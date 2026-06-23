1. Transactions and Memory Pool (Mempool)

Suppose Alice sends 2 BTC to Bob.

The transaction does not immediately enter a block.

Instead:

Wallet
  ↓
Bitcoin Network
  ↓
Mempool
  ↓
Block
  ↓
Blockchain
What is Mempool?

Think of a railway waiting room.

Passengers wait there before boarding a train.

Similarly:

Transactions wait in the mempool
Miners pick transactions from the mempool
Add them into a block

So:

Mempool = Waiting room for transactions
2. UTXO (Unspent Transaction Output)

This confuses many students, but it's actually easy.

Real-Life Example

You have:

₹500 note

You buy something worth:

₹100

You give:

₹500

Shopkeeper returns:

₹400

Now:

₹500 is spent
₹400 remains

The ₹400 can be used later.

Bitcoin works similarly.

Example 1

Bob owns:

2 BTC

Bob sends:

2 BTC → Alice

After transaction:

Bob = 0 BTC
Alice = 2 BTC

Alice now has an:

Unspent Transaction Output (UTXO)

because she hasn't spent it yet.

Example 2

Bob owns:

2 BTC
+
3 BTC
=
5 BTC

These are two separate UTXOs.

Now Bob wants to send:

4 BTC

to Alice.

Bob can use:

2 BTC
+
3 BTC
=
5 BTC

as input.

Transaction becomes:

Input
5 BTC
Outputs
4 BTC → Alice
1 BTC → Bob (change)

Exactly like getting ₹400 change after spending ₹500.

Important Formula
Inputs

Money entering transaction.

Outputs

Money leaving transaction.

Example:

Input = 5 BTC

Outputs:
4 BTC → Alice
1 BTC → Bob
Why UTXO is Important?

Because Bitcoin can:

✅ Check balance

✅ Prevent double spending

✅ Track coin history

Interview Answer

UTXO (Unspent Transaction Output) is the amount of bitcoin received in a transaction that has not yet been spent and can be used as input for future transactions.

3. Proof of Work (PoW)

This is the heart of Bitcoin.

Earlier we learned:

Many miners create blocks.

Question:

Which block should be accepted?

Bitcoin solves this using:

Proof of Work (PoW)
Simple Idea

Imagine:

100 students.

Teacher says:

Solve this difficult puzzle.

First student to solve it:

Wins.

Same thing happens in Bitcoin.

Many miners compete.

First miner solving the puzzle:

Becomes Leader

and can add the block.

Why Called Proof of Work?

Because miner proves:

"I actually did the work."

by showing the solution.

Hence:

Proof of Work
4. What is the Cryptographic Puzzle?

The puzzle is:

Find a hash value that starts with many zeros.

Example:

0000000000000ABC...

Valid.

But:

8A7B1234...

Invalid.

Not enough leading zeros.

How Miners Solve It?

Remember block header?

Contains:

Timestamp
Merkle Root
Previous Hash
Nonce

Miner changes:

Nonce

and recalculates hash.

Example:

Nonce = 1
Hash = AB34...

Not valid.

Nonce = 2
Hash = F234...

Not valid.

Nonce = 3
Hash = 00000000ABCD...

Valid.

Winner found.

What is Nonce?

Nonce = Number used once.

Simple meaning:

A trial number miners keep changing.

Think:

Trying passwords.

1234
1235
1236
1237
...

Until correct one appears.

Nonce works similarly.

Why Is Mining Hard?

Because of the:

Avalanche Effect

Small nonce change →

Completely different hash.

Example:

Nonce 10
Hash = A12F...
Nonce 11
Hash = 89BC...

Totally different.

No prediction possible.

Only:

Try
Try
Try
Try
5. Bitcoin Mining

Mining means:

Solving PoW puzzle and creating blocks.

Miners:

Take transactions from mempool
Create block
Try nonce values
Find solution
Publish block
Why Do Miners Mine?

Because they get rewards.

Earlier reward:

50 BTC

Then:

25 BTC

Then:

12.5 BTC

Then:

6.25 BTC

Reward halves roughly every 4 years.

This is called:

Bitcoin Halving
Maximum Bitcoin Supply

Only:

21 Million BTC

can ever exist.

Around year:

2140

all bitcoins will be mined.

After that:

Miners earn mainly from transaction fees.

6. Difficulty

Suppose only 10 miners exist.

Puzzle becomes easy.

Blocks appear quickly.

Suppose 1 million miners join.

Blocks appear too quickly.

This would break Bitcoin's design.

Bitcoin wants:

1 Block ≈ 10 Minutes

Always.

Solution?

Difficulty Adjustment

If blocks are found too fast:

Increase difficulty

More zeros needed.

If blocks are found too slowly:

Decrease difficulty

Fewer zeros needed.

Bitcoin adjusts difficulty every:

2016 blocks
7. Mining Pools

Today mining is extremely difficult.

One laptop cannot compete.

Many miners join together.

Miner A
Miner B
Miner C
Miner D

↓

Combine power

↓

Mining Pool

If pool wins:

Reward is shared.

8. Fork

Fork means:

Blockchain splits into branches.

Example:

Two miners find valid blocks at almost the same time.

Block A
Block B

Now chain splits.

9. Soft Fork

Temporary split.

Network later chooses one branch.

Other branch disappears.

Bitcoin follows:

Longest Chain Rule

Example:

Branch A = 102 blocks
Branch B = 101 blocks

Winner:

Branch A

Branch B is discarded.

Stale Block

Discarded block.

Example:

Branch B block

No reward.

Not used.

Called:

Stale Block
Orphan Block

A block with no valid parent block.

Called:

Orphan Block
10. Hard Fork

Permanent split.

Creates two separate blockchains.

Think:

One school becomes:

School A
School B

Both continue separately.

Hard Fork:

Old Chain
      ↓
   Split
   /    \
Chain1 Chain2

Permanent separation.

11. Bitcoin Limitations
1. Expensive Hardware

Mining requires powerful machines.

2. Huge Electricity Usage

Consumes enormous power.

3. 51% Attack

If someone controls:

More than 50%

of total mining power,

they may manipulate the network.

This is called:

51% Attack
4. Slow Transactions

Bitcoin creates:

1 block every 10 minutes

For strong confirmation:

6 confirmations
≈ 1 hour
5. Environmental Impact

High energy consumption.

More pollution.

6. Limited Programmability

Bitcoin mainly supports:

Digital Payments

Unlike Ethereum, it is not designed for complex decentralized applications.