1. What is Consensus?
Simple Meaning

Consensus = Agreement

Example:

You and your friends want to watch a movie.

Some choose:

Leo
Jailer
Vikram

Finally everyone agrees on:

Vikram

That final agreement is called:

Consensus
In Blockchain

Thousands of nodes exist.

Each node may create a different candidate block.

Question:

Which block should become Block 100?

Only ONE block can be selected.

The process of choosing that block is called:

Consensus
2. Why Do We Need Consensus?

Suppose blockchain currently has:

Block 1
Block 2
...
Block 99

Now many nodes receive new transactions.

Node A creates:
Block 100A
Node B creates:
Block 100B
Node C creates:
Block 100C

If everyone adds their own block:

Chain A
Chain B
Chain C

Now there are multiple blockchains.

This is bad.

Blockchain needs:

One Blockchain
One Version
One Truth

Consensus solves this problem.

3. Types of Consensus

The notes mention two categories.

A. Voting-Based Consensus

Think:

Class Leader Election

Everyone votes.

Winner gets selected.

Examples:

PBFT
RAFT

Used mostly in:

Private Blockchains

Because fewer participants exist.

B. Lottery-Based Consensus

Think:

Lucky Draw

One participant wins randomly based on certain rules.

Examples:

Proof of Work (PoW)
Proof of Stake (PoS)

Used in:

Public Blockchains

Like:

Bitcoin

and

Ethereum

4. Two Generals Problem

This is a famous computer science problem.

Don't worry about the complicated story.

Focus on the idea.

Scenario

Two generals want to attack a city.

To win:

Both must attack at the same time.

General 1 sends:
Attack Monday Morning
General 2 replies:
Okay, confirmed.

Now General 1 knows.

But:

Does General 2 know that General 1 received the confirmation?

No.

So General 1 sends:

I received your confirmation.

Now another question:

Did General 2 receive that message?

No one knows.

Again another confirmation is needed.

Then another.

Then another.

Forever.

Confirm
Confirm confirmation
Confirm confirmation confirmation
...

Infinite loop.

Main Idea

In distributed systems:

You can never be 100% sure that every message reached everyone.

This is called:

Two Generals Problem
Interview Answer

The Two Generals Problem demonstrates the difficulty of achieving perfect agreement in a distributed system where communication messages may be lost.

5. Byzantine Generals Problem

This is even more important.

Scenario

Suppose:

3 generals.

Need to decide:

Attack
or
Retreat
Honest Situation

General A:

Attack

General B:

Attack

General C:

Attack

Everyone agrees.

Easy.

Problem Situation

Suppose General A is malicious.

To General B:

Attack

To General C:

Retreat

Now:

B thinks Attack
C thinks Retreat

No agreement.

Another possibility:

Commander is honest.

But one lieutenant lies.

Same issue.

Network becomes confused.

Main Idea

Some participants may:

Lie
Send wrong messages
Be hacked
Be faulty

Question:

Can the network still reach agreement?

This is the Byzantine Generals Problem.

Easy Real-Life Example

Imagine a WhatsApp group.

5 friends deciding where to eat.

4 friends say:

Let's go to Pizza Hut

One friend intentionally lies:

Everyone agreed KFC.

Now confusion begins.

Blockchain faces the same problem.

6. What is a Byzantine Node?

A Byzantine node is:

A faulty or malicious node.

Examples:

Hacked computer
Broken software
Wrong data
Malicious participant

Example:

100 nodes.

95 honest.

5 malicious.

Those 5 try to spread false information.

Those are Byzantine nodes.

7. Byzantine Fault Tolerance (BFT)

This is the solution.

Definition

Byzantine Fault Tolerance is the ability of a system to continue working correctly even when some nodes are faulty or malicious.

Think:

Class of 100 students.

5 students give wrong answers.

95 students give correct answers.

Teacher trusts:

95 > 5

Correct decision is still possible.

Similarly:

Blockchain can still function even if some nodes are dishonest.

Why BFT is Important?

Blockchain is:

Decentralized

Anyone can join.

Because anyone can join:

Hackers can join
Malicious users can join
Faulty systems can join

Therefore blockchain must tolerate bad actors.

That's exactly what BFT provides.

Complete Flow of This Unit
Many Nodes
      ↓
Need Agreement
      ↓
Consensus
      ↓
Problem:
Can nodes agree?
      ↓
Two Generals Problem
      ↓
Hard to guarantee communication
      ↓
Byzantine Generals Problem
      ↓
Some nodes may lie
      ↓
Need Solution
      ↓
Byzantine Fault Tolerance
      ↓
Consensus Algorithms
(PoW, PoS, PBFT etc.)
2-Minute Exam Revision
Consensus

A process through which all nodes in a blockchain network agree on the next block to be added.

Why is consensus needed?

To ensure only one valid version of the blockchain exists.

Two Generals Problem

Shows the difficulty of achieving perfect agreement when messages may be lost.

Byzantine Generals Problem

Shows the difficulty of reaching agreement when some participants are malicious or faulty.

Byzantine Node

A faulty or malicious node that sends incorrect information.

Byzantine Fault Tolerance (BFT)

The ability of a distributed system to reach consensus even when some nodes behave maliciously or fail.

This section is much easier than the previous one. It mainly covers:

Types of Blockchain
Bitcoin
Types of Nodes in Bitcoin Network
1. Types of Blockchain

There are mainly 3 types of blockchains:

1. Public Blockchain
2. Private Blockchain
3. Hybrid Blockchain
2. Public Blockchain
Simple Meaning

Anyone can join.

Anyone can:

✅ Read data

✅ Send transactions

✅ Verify transactions

✅ Participate in maintaining the network

No permission needed.

Real-Life Example

Think of a public park.

Anyone can enter.

Nobody needs special approval.

Examples
Bitcoin
Ethereum

These are public blockchains.

Characteristics
Open to everyone
Fully decentralized
Transparent
Secure
Usually has cryptocurrency tokens

Example:

Bitcoin rewards miners with Bitcoin.

Easy Interview Answer

A public blockchain is an open blockchain network where anyone can participate without permission.

3. Private Blockchain
Simple Meaning

Only approved people can join.

Permission is required.

Real-Life Example

Think of a college WhatsApp group.

Only students added by the admin can join.

Not everyone can enter.

Characteristics
Restricted access
Permission required
More centralized
Faster than public blockchains
Data is private
Example

Suppose:

A bank creates its own blockchain.

Only:

Bank employees
Branch offices

can access it.

Public users cannot.

Easy Interview Answer

A private blockchain is a permissioned blockchain where only authorized participants can access and perform operations.

4. Hybrid Blockchain
Simple Meaning

Combination of:

Public Blockchain
+
Private Blockchain
Real-Life Example

Think of a company.

Some information is public:

Company Website

Some information is private:

Employee Salary Data

Hybrid blockchain works similarly.

Characteristics

Some data:

✅ Public

Some data:

✅ Private

Best of both worlds.

Easy Interview Answer

A hybrid blockchain combines the transparency of public blockchains with the privacy of private blockchains.

Quick Comparison
Feature	Public	Private	Hybrid
Anyone Join?	Yes	No	Partially
Permission Needed?	No	Yes	Partial
Transparency	High	Low	Medium
Decentralization	High	Low	Medium
5. What is Bitcoin?

This is one of the most important blockchain questions.

Simple Definition

Bitcoin is the world's first cryptocurrency.

Introduced in:

2008

by:

Satoshi Nakamoto

Purpose

Send money directly without:

Banks
Governments
Middlemen
Traditional Way
Alice
 ↓
Bank
 ↓
Bob
Bitcoin Way
Alice
 ↓
Bitcoin Network
 ↓
Bob

No bank involved.

Key Features of Bitcoin
1. Decentralized

No central authority.

2. Peer-to-Peer

Direct transactions.

3. Transparent

Everyone can verify transactions.

4. Limited Supply

Maximum:

21 Million Bitcoins

Only.

No more can be created.

This scarcity helps create value.

5. Irreversible Transactions

Once sent:

Cannot be reversed.

Easy Interview Answer

Bitcoin is a decentralized digital currency introduced by Satoshi Nakamoto in 2008 that allows peer-to-peer transactions without banks or intermediaries.

6. Nodes in Bitcoin Network

You already know:

Node = Computer participating in blockchain.

Bitcoin has different types of nodes.

7. Full Node
Simple Meaning

Stores the complete blockchain.

Example:

Block 1
Block 2
...
Block 1,000,000

Everything is stored.

Advantages

Can independently verify transactions.

Doesn't depend on anyone.

Drawback

Requires large storage space.

Easy Interview Answer

A full node stores the complete blockchain and independently verifies all transactions.

8. Lightweight Node

Also called:

SPV Node

(Simplified Payment Verification)

Simple Meaning

Stores only block headers.

Not full blocks.

Instead of storing:

100 GB

It stores only essential information.

Advantage

Less storage needed.

Good for mobile devices.

Disadvantage

Depends on full nodes for some information.

Easy Interview Answer

A lightweight node stores only block headers and uses SPV to verify transactions without storing the complete blockchain.

9. Miner Node

This is the node that performs:

Mining

(You'll study this in the next units.)

Job
Collect transactions
Create blocks
Compete to add blocks
Earn rewards
Needs

Powerful hardware.

Example

Miner finds the correct solution.

Network accepts block.

Miner gets Bitcoin reward.

Easy Interview Answer

A miner node participates in the mining process and creates new blocks by executing the consensus algorithm.

10. Router Node

This is easier.

Think of:

Traffic Police

It helps route information.