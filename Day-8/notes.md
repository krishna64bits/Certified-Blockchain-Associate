Reentrancy is one of the most famous and dangerous smart contract vulnerabilities. Once you understand the basic idea, everything else becomes much easier.

Imagine a Real-Life Example

Suppose you go to an ATM.

The ATM is supposed to do this:

Check your account balance.
Deduct ₹1000 from your account.
Give you ₹1000.

Everything is fine.

Now imagine a broken ATM that does this instead:

Check your balance.
Give you ₹1000.
Deduct ₹1000.

Notice the problem?

Before the ATM updates your balance, you somehow press the button again and ask for another ₹1000.

The ATM checks your balance again.

It still thinks you have money because it hasn't updated yet.

So it gives another ₹1000.

You repeat this many times.

Finally it deducts only one withdrawal from your account.

You stole money.

This is exactly what Reentrancy is.

In Smart Contracts

A smart contract has something like this:

balances[Alice] = 100;

Alice calls

withdraw(100);

The contract does

Check balance

↓

Send ETH

↓

Update balance

The dangerous part is

Send ETH

because sending ETH means another contract gets control.

That contract can immediately call back.

This is called

Re-entering the function.

That's why it's called Reentrancy Attack.

Step-by-Step Attack

Suppose a vault has

100 ETH

Attacker deposited

1 ETH

Vault stores

balance[attacker] = 1

Attacker calls

withdraw()

Vault checks

Yes

You have 1 ETH

Instead of updating balance first,

it sends ETH.

send(1 ETH)

Now attacker receives control.

Instead of accepting the ETH quietly,

the attacker immediately calls

withdraw()

again.

The vault checks

balance[attacker]

Still

1 ETH

because it hasn't been updated yet.

So it sends another ETH.

The attacker repeats

withdraw()

↓

receive ETH

↓

withdraw()

↓

receive ETH

↓

withdraw()

again and again.

Finally,

the first function finishes

and only then

balance = 0

But by then,

the attacker already received

10 ETH

instead of

1 ETH.
Visual Diagram
Attacker
    |
    | withdraw()
    |
Vault
    |
    | Check balance ✔
    |
    | Send ETH -----------+
    |                     |
    |                     |
    |              Attacker receives ETH
    |                     |
    |                     |
    |<------ withdraw() again
    |
    | Check balance ✔
    |
    | Send ETH again
    |
    | ...

The vault never got a chance to reduce the balance.

Vulnerable Code
function withdraw(uint amount) public {

    require(balance[msg.sender] >= amount);

    payable(msg.sender).transfer(amount);

    balance[msg.sender] -= amount;
}

Look carefully.

Check

↓

Transfer

↓

Update

This is wrong.

Safe Code

Instead,

do this.

function withdraw(uint amount) public {

    require(balance[msg.sender] >= amount);

    balance[msg.sender] -= amount;

    payable(msg.sender).transfer(amount);
}

Now the order is

Check

↓

Update

↓

Transfer

Even if the attacker comes back,

their balance is already

0

The attack fails.

Why Does Sending ETH Cause Problems?

When Solidity executes

call()

or

transfer()

or

send()

it hands execution to another address.

If that address is a smart contract,

it can execute its own code.

Example:

receive() external payable {

}

or

fallback() external payable {

}

These functions run automatically when ETH is received.

An attacker writes

receive() external payable {

    vault.withdraw();
}

So receiving ETH automatically starts another withdrawal.

Example Attack Contract
contract Attack {

    Vault public vault;

    constructor(address _vault) {
        vault = Vault(_vault);
    }

    function attack() public {

        vault.deposit{value:1 ether}();

        vault.withdraw(1 ether);
    }

    receive() external payable {

        if(address(vault).balance >= 1 ether){

            vault.withdraw(1 ether);

        }
    }
}

Notice

receive()

↓

withdraw()

↓

receive()

↓

withdraw()

This creates a loop.

Why Doesn't It Stop?

Because

the vault still thinks

balance = 1 ETH

until the first function finishes.

Checks-Effects-Interactions Pattern

Every Solidity developer memorizes this.

Step 1

Check everything.

require(...)
Step 2

Update storage.

balance -= amount;
Step 3

Interact with other contracts.

transfer()
call()

Always remember:

Never call another contract before updating your own state.

ReentrancyGuard

OpenZeppelin provides a lock.

contract Vault is ReentrancyGuard {

    function withdraw()
        public
        nonReentrant
    {

    }

}

Imagine a bathroom.

One person enters.

The door locks.

No one else can enter until the first person leaves.

That's exactly what nonReentrant does.

Function starts

↓

Lock = true

↓

Any second call?

↓

Rejected

↓

Function ends

↓

Lock = false
Types of Reentrancy
1. Single-Function Reentrancy

The same function is called repeatedly.

withdraw()

↓

withdraw()

↓

withdraw()

This is the classic attack.

2. Cross-Function Reentrancy

Instead of calling withdraw() again, the attacker calls a different function before the first one finishes.

Example:

withdraw()

↓

deposit()

↓

claimReward()

If these functions share the same state, they can still be exploited.

3. Cross-Contract Reentrancy

The attack goes through multiple contracts.

Vault

↓

Strategy

↓

DEX

↓

Attacker

↓

Vault again

This is common in complex DeFi systems.

4. Read-Only Reentrancy

No money is stolen directly.

Instead, the attacker tricks a contract into reading temporary or inconsistent values during a callback. This can manipulate things like prices, rewards, or voting power.

Simple Memory Trick

Remember this rule:

Check → Update → External Call

❌ Wrong:

Check

↓

External Call

↓

Update

✔️ Correct:

Check

↓

Update

↓

External Call
What is an External Call?

An external call means your smart contract is asking another contract to do something.

Think of it like this:

Your Contract
      |
      | "Hey, send tokens."
      |
      v
Another Contract

Examples:

token.transfer(...)
otherContract.deposit(...)
address.call(...)
delegatecall(...)
staticcall(...)

All of these are external calls because your contract is communicating with another contract.

Why are External Calls Dangerous?

Because you don't control the other contract.

Imagine you call your friend.

You expect him to say:

"Okay."

Instead he might

hang up
lie
prank you
call you back immediately
never answer

You cannot predict his behavior.

Smart contracts are the same.

When you call another contract,

you are trusting it.

That trust may be wrong.

The Biggest Rule

Every external contract is untrusted.

Even if it is

ERC20
NFT
DEX
Bridge
Flash Loan
Oracle

Treat it as if it could be malicious.

What Does "Unchecked External Call" Mean?

It simply means

You called another contract without checking what happened.

Example

token.transfer(msg.sender,100);

Programmer assumes

Transfer succeeded.

But...

Did it really?

Maybe yes.

Maybe no.

The programmer never checked.

That is called an Unchecked External Call.

Example

Suppose I tell my friend

Go buy me pizza.

He says nothing.

I immediately assume

Great!
Pizza is coming.

One hour later...

No pizza.

Why?

Because I never checked whether he actually agreed.

Smart contracts make the same mistake.

ERC20 Transfer

Most ERC20 tokens have

function transfer(address,uint)
returns(bool)

Notice

returns(bool)

That means

true

or

false

Example

bool ok = token.transfer(user,100);

If

ok == true

Transfer worked.

If

ok == false

Transfer failed.

Vulnerable Code
token.transfer(msg.sender, amount);

rewards[msg.sender]=0;

Looks okay.

But what if

transfer()

returns

false

?

The programmer ignored it.

Imagine

Reward = 100

Transfer failed.

No tokens moved.

Yet the contract still does

reward=0

User lost everything.

Always check.

bool ok = token.transfer(...);

require(ok);

Now if transfer fails,

everything stops.

What if the Other Contract is Malicious?

This is another huge concept.

Suppose

Vault

calls

Malicious Token

Instead of simply sending tokens,

the malicious token executes its own code.

Example

Vault

↓

token.transfer()

↓

Malicious Token

↓

Runs attack code

Your contract expected

Transfer completed.

Instead

the token starts attacking you.

Reentrancy

This is where SC08 comes in.

Suppose your contract does

token.transfer(...);

reward=0;

During

transfer()

the token executes

claim()

again.

Because

reward

hasn't become

0

yet,

the attacker claims again.

This is why

Unchecked External Calls

Wrong order

=

Reentrancy attack.

Silent Failure

This is another important concept.

Suppose

bool ok = token.transfer(...);

returns

false

Programmer ignores it.

Program continues.

Nobody knows transfer failed.

This is called

Silent Failure

Nothing crashes.

No error.

But nothing worked either.

Those bugs are dangerous because they often go unnoticed.

Why Can Transfer Fail?

Many reasons.

Maybe

No balance

Maybe

Token paused

Maybe

Blacklist

Maybe

Malicious contract

Maybe

Out of gas

Maybe

Token intentionally returned false

You must handle all these cases.

Low-Level Calls

Now comes another concept.

Instead of

token.transfer(...)

some developers use

address.call(...)

Example

(bool success,) =
address(target).call(data);

Notice

success

If you ignore it

address.call(data);

You don't know

Did it execute?
Did it fail?
Did it revert?

Always check

require(success);
delegatecall

This is one of Solidity's most powerful and dangerous features.

Normally

Contract A

↓

calls

↓

Contract B

B changes its own storage.

With

delegatecall

B executes its code

but modifies

A's storage.

Think of it like hiring a temporary worker to rearrange your own house. If the worker is malicious, they can move or steal anything inside your house.

Because of that, never delegatecall untrusted contracts.

staticcall

This is a read-only call.

Example

price = oracle.getPrice();

The called contract is not allowed to modify state.

It can only return data.

Still,

it can

fail
revert
return wrong data

So check its results and trust only reliable sources.

High-Level Calls

These are easier functions.

Examples

token.transfer()
token.approve()
NFT.safeTransferFrom()

They still make external calls underneath.

Don't assume they always succeed.

Hooks (Callbacks)

Some token standards automatically call another contract.

Example

ERC721 NFT

Alice sends NFT

↓

Receiver contract

↓

onERC721Received()

That function runs automatically.

Same with

ERC777

transfer()

↓

tokensReceived()

The receiver can execute arbitrary code.

This is another place where reentrancy can happen.

Flash Loan Callback

Suppose you borrow

1 million USDC

The protocol gives you money.

Then immediately calls

executeOperation()

inside your contract.

Protocol

↓

Borrow money

↓

executeOperation()

↓

Repay

During

executeOperation()

your contract can do anything.

Protocols must assume that callback is fully untrusted.

Arbitrary Address

This is another dangerous concept.

Imagine the protocol lets users choose any address to call.

Example

call(routerAddress);

User provides

routerAddress

instead of the protocol.

Honest user

Uniswap Router

Attacker

AttackContract

The protocol blindly calls it.

Now the attacker controls what code runs.

This happened in real attacks.

Never allow arbitrary external addresses without validation.

Push vs Pull Payments
Push

The contract sends money automatically.

Contract

↓

Send ETH

↓

User

Problems:

receiver can reject it
receiver can re-enter
receiver can consume gas
Pull

Contract records

User can withdraw 100 ETH

User later calls

withdraw()

to receive it.

Contract

↓

Record reward

↓

User decides when to withdraw

This is much safer.

OpenZeppelin SafeERC20

Some old ERC20 tokens don't return

true

or

false

Some revert.

Some return nothing.

Handling all these differences manually is error-prone.

That's why developers use OpenZeppelin's SafeERC20 library, which safely wraps token operations and correctly handles these token behaviors.

Checks-Effects-Interactions

This is the golden rule.

Checks

Verify everything.

require(balance>=amount);
Effects

Update storage.

balance-=amount;
Interactions

Call another contract.

token.transfer(...)

Always remember this order:

Checks

↓

Effects

↓

Interactions

Never reverse it.

Everything Together (Flow)
User

↓

Calls claim()

↓

Contract checks reward

↓

Contract updates reward = 0

↓

Contract calls token.transfer()

↓

Transfer succeeds?

       ↓

Yes → Finish

No → Revert transaction

If the external call is malicious and tries to call back into your contract, your important state has already been updated, reducing the risk of reentrancy.