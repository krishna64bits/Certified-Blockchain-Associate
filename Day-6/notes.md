DApps (Decentralized Applications)
What is a DApp?

A DApp (Decentralized Application) is an application that runs on a blockchain instead of a central server.

Normal App

Instagram → Meta Server → Database

Everything is controlled by one company.

DApp

User ↔ Blockchain ↔ Smart Contract

No central authority controls it.

Examples:

Uniswap
CryptoKitties
MakerDAO
Why use DApps?

Instead of trusting a company, users trust the blockchain.

Benefits:

No middleman
Transparent
Secure
Cannot easily be modified
Works 24/7
5 Layers of a DApp

Think of building a house.

Layer 5 → Operating System
Layer 4 → Ethereum Virtual Machine (EVM)
Layer 3 → Smart Contract
Layer 2 → Web3
Layer 1 → Front End

Let's understand each.

1. Front End

This is what users see.

Examples:

Buttons
Textboxes
Login screen
Wallet Connect button

Built using:

HTML
CSS
JavaScript
React

Example:

You open a DApp.

You click

"Send 2 ETH"

That button belongs to the Front End.

2. Web3 Layer

The Front End cannot directly talk to Ethereum.

It needs a translator.

That translator is Web3 libraries.

Examples:

Web3.js
Ethers.js

These communicate using

HTTP
WebSocket
IPC

They send blockchain requests like:

Read balance
Send transaction
Call smart contract

Think of Web3 as a bridge.

User
↓

Website
↓

Web3
↓

Ethereum
3. Smart Contract

This is the heart of Ethereum.

A smart contract is simply a program stored on Ethereum.

Example

If Hari sends 2 ETH
↓

Transfer NFT

Nobody manually approves it.

The blockchain automatically executes it.

What can Smart Contracts do?

They can

Send ETH
Store data
Create tokens
Voting
NFT marketplace
Banking
Games
Why are Smart Contracts special?

Because they are

✅ Automatic

They execute themselves.

Example

If payment received

↓

Deliver product

No employee needed.

Transparent

Everyone can read the code.

Tamper Proof

Once deployed

Nobody can secretly edit it.

Immutable

After deployment

Code cannot normally be changed.

No Middleman

Traditional

Buyer → Bank → Seller

Ethereum

Buyer → Smart Contract → Seller

Features of Smart Contracts
1. Transparent

Everyone can verify the rules.

2. Resistant to Failure

Even if one node crashes

Thousands of other nodes still run it.

3. Tamper Proof

Nobody changes deployed code.

4. Fraud Reduction

Rules execute automatically.

No cheating.

5. Zero Third Party

No bank.

No broker.

No lawyer.

6. Cost Efficient

Less paperwork.

Less commission.

7. Record Keeping

Everything stays on blockchain forever.

8. Anonymity

People are identified using wallet addresses.

Not names.

9. Self Executing

Contract runs automatically.

10. Self Verifying

Blockchain checks whether all conditions are satisfied.

11. Immutable

Cannot normally be changed after deployment.

12. Executes only if Conditions are True

Example

If payment == received

↓

Deliver NFT

Else

↓

Nothing happens.
4. Ethereum Virtual Machine (EVM)

Imagine Ethereum as a huge computer.

The CPU of this computer is called the Ethereum Virtual Machine (EVM).

It executes smart contracts.

Example

You deploy

Hello.sol

↓

EVM reads it

↓

Runs it

↓

Returns output.

Every Ethereum node contains an EVM.

Thousands of computers execute exactly the same code.

Why EVM?

Without EVM

Ethereum cannot execute programs.

It would only store transactions.

5. Operating System

This is the actual operating system.

Examples

Windows
Linux
macOS

The EVM runs on these operating systems.

Complete DApp Flow
User

↓

Front End (Website)

↓

Web3

↓

Ethereum Network

↓

EVM

↓

Smart Contract

↓

Blockchain updates

↓

Result comes back

↓

Website displays result
Remix IDE

Now let's learn how developers create smart contracts.

Remix IDE is an online software for writing Ethereum smart contracts.

Website:

https://remix.ethereum.org

No installation needed.

Runs inside your browser.

What can Remix do?

It can

Write Solidity code
Compile code
Deploy contracts
Test contracts
Debug contracts

Everything in one place.

Blockchain Environments inside Remix

Remix supports different environments.

1. Remix VM

A fake blockchain.

Used for testing.

Internet not required.

Every refresh creates a fresh blockchain.

Best for beginners.

2. Injected Provider (MetaMask)

Connects Remix to your MetaMask wallet.

Deploys contracts to Ethereum Testnet or Mainnet.

3. Hardhat Provider

Connects Remix to a local Hardhat blockchain.

4. Ganache Provider

Connects Remix to Ganache.

5. Foundry Provider

Connects Remix to Foundry Anvil.

6. WalletConnect

Connect mobile wallets.

7. External HTTP Provider

Connects to your own Ethereum node like Geth.

PART 2 – Solidity, Remix Compiler, Deployment, MetaMask, Etherscan & Ganache
What is Solidity?

Before Ethereum, Bitcoin could only transfer money.

Ethereum introduced Smart Contracts, but computers need a programming language to understand instructions.

That language is Solidity.

Definition:
Solidity is a high-level, object-oriented programming language used to write smart contracts on Ethereum.

It was proposed by Gavin Wood in 2014.

Why is Solidity popular?

Because it is:

Similar to JavaScript
Easy to learn for web developers
Designed specifically for Ethereum
Supports smart contracts
Has a huge developer community
Features of Solidity
1. JavaScript-like Syntax

Example:

uint age = 20;

Looks similar to JavaScript.

2. Statically Typed

You must specify data types.

Correct:

uint age = 20;

Wrong:

age = 20;

The compiler won't allow it.

3. Supports Inheritance

Just like Java or C++.

Example:

Animal
   ↑
 Dog

The child contract inherits functions from the parent.

4. Supports Libraries

Instead of writing the same code repeatedly,

You can reuse library functions.

5. Supports Complex Data Types

Examples

Mapping
mapping(address => uint)

Stores balances.

Struct

Stores multiple values.

Example

Student

Name

Age

Marks
What is Vyper?

Vyper is another Ethereum smart contract language.

Instead of JavaScript,

Its syntax looks like Python.

Example

x: uint256 = 10
Goals of Vyper

Unlike Solidity,

Vyper focuses on

Security
Simplicity
Easy auditing
Features
Overflow Checking

If numbers become too large,

It automatically checks.

Example

Instead of

99999999999999999999

causing problems,

Vyper prevents overflow.

Fixed Point Numbers

Supports decimal calculations safely.

Predictable Gas

Developers can calculate the maximum gas before execution.

Very useful.

Strongly Typed

Every variable must have a type.

Small Compiler

Less code

↓

Fewer bugs

↓

Better security

Solidity vs Vyper
Solidity	Vyper
JavaScript-like	Python-like
More features	Simpler
Most popular	Less popular
Supports inheritance	Doesn't support many advanced features
Large community	Small community
Remix IDE

Think of Remix as Microsoft Word,

but instead of writing documents,

you write smart contracts.

It runs completely inside your browser.

Main Sections of Remix

There are four important parts.

1. File Explorer

Like Windows File Explorer.

You can

Create files
Delete files
Open files

Example

Hello.sol
2. Code Editor

This is where you write Solidity code.

Example

pragma solidity ^0.8.0;

contract Hello {

}
3. Compiler

Turns Solidity code into machine code.

4. Deploy & Run

Uploads the smart contract onto Ethereum.

Sample Solidity Program
pragma solidity ^0.5.16;

contract Test {

string message="Hello World";

function getMessage()
public
view
returns(string memory)
{
return message;
}

}

Let's understand every line.

pragma solidity
pragma solidity ^0.5.16;

This specifies the Solidity version.

Think of it like

"I wrote this program for Version 0.5.16."

contract
contract Test

Creates a smart contract named Test.

Just like

class Student

in Java.

State Variable
string message="Hello World";

This variable is permanently stored on the blockchain.

That is why it is called a state variable.

Function
function getMessage()

Creates a function.

public

Means

Everyone can call it.

view

Means

The function only reads data.

It does NOT change blockchain data.

returns
returns(string memory)

The function returns a string.

return

Returns

Hello World
Remix Compiler

Once code is written,

we must compile it.

Compilation means

Convert Solidity code into machine-readable code.

Compiler Options
Compiler Version

Must match your code.

Example

pragma solidity ^0.8.20

Compiler

0.8.20

Language

Choose

Solidity

or

Vyper

EVM Version

Specifies which Ethereum version to support.

Auto Compile

Whenever you type,

the code automatically compiles.

Very useful.

Hide Warnings

Hides warning messages.

Compile Button

Compiles your smart contract.

If errors exist,

it tells you exactly where.

What happens after Successful Compilation?

You'll see:

Contract

Shows all compiled contracts.

ABI

Very important interview question.

ABI stands for

Application Binary Interface

Think of it as a menu card.

Example

Restaurant Menu

Pizza
Burger
Juice

Similarly,

ABI lists all smart contract functions.

Wallets use the ABI to know how to communicate with the contract.

Bytecode

This is machine code.

The EVM understands only Bytecode.

Flow:

Solidity Code

↓

Compiler

↓

Bytecode

↓

EVM
Compilation Details

Contains

ABI
Bytecode
Metadata
Compiler information
Deploy & Run Transactions

Now we deploy.

Deploy means

Upload the smart contract to Ethereum.

Environment

Different blockchain choices.

Remix VM

Fake blockchain.

Best for testing.

Injected Provider

Uses MetaMask.

Deploys on Ethereum.

External HTTP

Connects to your own Ethereum node.

Hardhat

Connects to Hardhat blockchain.

Ganache

Connects to Ganache.

Foundry

Connects to Foundry.

Account

Shows the wallet you're using.

Example

0x12A...
Gas Limit

Maximum gas you're willing to spend.

Example

Gas Needed

20,000

Gas Limit

25,000

Transaction succeeds.

If limit

10,000

Transaction fails.

Value

ETH sent to the smart contract.

Example

Send

5 ETH

while deploying.

Deploy Button

Creates the smart contract.

After deployment

You receive

Contract Address

Example

0x89A7...
At Address

Suppose your friend already deployed the contract.

You only know its address.

Paste it here,

and Remix connects to that existing contract.

No need to deploy again.

Button Colors

Very important.

Blue Button

Only reads data.

No gas.

No transaction.

Example

getMessage()
Orange Button

Changes blockchain state.

Needs gas.

Creates a transaction.

Example

setMessage()
MetaMask

MetaMask is an Ethereum wallet.

It works as a browser extension.

Think of it like Google Pay,

but for Ethereum.

It lets you:

Store ETH
Send ETH
Receive ETH
Connect to DApps
Sign transactions
Light Client

MetaMask is called a Light Client.

Why?

Because it

doesn't download the full Ethereum blockchain.

Instead,

it communicates with other Ethereum nodes.

This saves storage and is much faster.

Creating a Wallet

When you install MetaMask,

you get two options:

Import Wallet

Already have a wallet?

Restore it.

Create Wallet

New wallet.

Creates

Public Address
Private Key
Seed Phrase
Password

Protects MetaMask on your device.

Important:

The password only unlocks the app on your device. It does not recover your wallet.

Seed Phrase

The Seed Phrase (Recovery Phrase) is usually 12 or 24 secret words.

Example:

apple
chair
river
...

It is the master key to your wallet.

Anyone with the seed phrase can access your funds.

Never share it with anyone.

Accounts in MetaMask

One wallet

↓

Many accounts.

Example

Account 1

Account 2

Account 3

All belong to the same wallet.

Sepolia Test Network

Ethereum Mainnet uses real ETH.

Developers don't want to waste real money.

So they use a test network.

Sepolia provides test ETH with no real-world value.

Developers get test ETH from a faucet.

Faucet

Think of a water tap.

Instead of water,

it gives free test ETH.

Only for development and testing.

Sending ETH

Steps

Select Account

↓

Click Send

↓

Choose Receiver

↓

Enter Amount

↓

Confirm

↓

Blockchain Processes Transaction
Restoring Wallet

Lost your computer?

No problem.

Install MetaMask again.

Enter your Seed Phrase.

Create a new password.

Your wallet and funds are restored.

Etherscan

Etherscan is a block explorer.

It lets anyone view blockchain data.

You can search by:

Wallet Address
Transaction Hash
Block Number
Contract Address

You can see:

Sender
Receiver
Amount
Gas Used
Status
Timestamp

It's like Google Search for Ethereum blockchain data.

Ganache

Ganache is a local Ethereum blockchain simulator.

It is mainly used for testing smart contracts without spending real ETH.

Features:

Creates 10 test accounts automatically.
Gives each account fake ETH.
Instantly mines blocks.
Lets you control gas price, gas limit, and network settings.
Perfect for learning and development.
Ganache Workspace

You can configure:

Workspace Name
RPC Server (host and port)
Network ID
Number of Accounts
ETH Balance per Account
Mnemonic (Seed Phrase)
Gas Limit
Gas Price
EVM Version
Mining Settings
Logs
Ganache Dashboard

You can inspect:

Accounts
Blocks
Transactions
Contracts
Events
Logs

This makes debugging much easier than using the real Ethereum network.