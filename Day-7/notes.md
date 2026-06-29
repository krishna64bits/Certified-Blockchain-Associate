Chapter 1: Why do we need Permissioned Blockchains?

Before understanding Hyperledger Fabric, first understand why it was created.

Public Blockchain (Bitcoin & Ethereum)

Imagine WhatsApp.

Anyone can create an account.
Anyone can join.
Anyone can send messages.

Public blockchains are similar.

Examples:

Bitcoin
Ethereum

Features:

Anyone can join.
Anyone can become a node.
Anyone can validate transactions.
No permission is required.

Because strangers are working together,

they need rewards.

So they use cryptocurrencies like

Bitcoin (BTC)
Ether (ETH)

to pay miners/validators.

Problem with Public Blockchain

Businesses don't always want this.

Imagine a bank.

Would a bank allow everyone in the world to see customer transactions?

No.

Imagine Amazon.

Would Amazon allow competitors to view supplier payments?

No.

Businesses need

privacy
control
fast performance

Public blockchains cannot provide all of these.

Therefore,

Permissioned Blockchain was created.

What is Permissioned Blockchain?

Permissioned means

Only approved members can enter.

Just like

A college classroom.

Anyone cannot simply walk in.

Only students with ID cards can enter.

Similarly,

only approved organizations can join a permissioned blockchain.

Features

Instead of

Everyone → Allowed

It becomes

Only Approved Members → Allowed

Therefore,

Nodes are

✅ Known

not anonymous.

Why is it faster?

Bitcoin

Thousands of computers

↓

Need consensus

↓

Very slow

Permissioned Blockchain

Only 10

20

50

Known nodes

↓

Consensus becomes very fast.

Why Businesses Prefer Permissioned Blockchain

The course gives four reasons.

Let's understand each.

1. Business Compatibility

Example

Suppose

Toyota

Honda

BMW

all have suppliers.

Toyota doesn't want Honda seeing supplier data.

Permissioned blockchain allows

Only authorized partners

to access data.

Think of Google Drive.

You can choose

Only specific people can view.

Exactly the same idea.

2. Higher Throughput

Throughput means

Number of transactions processed per second (TPS).

Bitcoin

≈ 7 TPS

Ethereum

≈15-30 TPS

Businesses may require

1000+

5000+

TPS.

Permissioned blockchains can process thousands of TPS.

Because

Very few trusted nodes.

3. Defined Governance

Governance means

Who decides the rules?

Public Blockchain

Community voting

Very difficult.

Permissioned Blockchain

Enterprise decides.

Example

Company updates rules.

Everyone follows.

Simple.

4. Cost Effective

Bitcoin

Mining

↓

Electricity

↓

Rewards

↓

Transaction fees.

Permissioned Blockchain

No mining

No cryptocurrency required

No miners

Therefore

Very low transaction fees.

Examples of Permissioned Blockchain

Your notes mention three.

Hyperledger Fabric
Hyperledger Sawtooth
R3 Corda

Remember these.

LF Decentralized Trust (LFDT)

Earlier

Hyperledger projects were under Linux Foundation Hyperledger.

Now

They come under

LF Decentralized Trust (LFDT).

Think of LFDT as

A big umbrella organization

supporting enterprise blockchain projects.

What does LFDT do?

It develops

Blockchain frameworks
Identity tools
Security libraries
Digital trust technologies

Everything is

Open Source.

Projects under LFDT

You don't need to memorize every project deeply.

Know what each one does.

Hiero

Open-source code for Hedera.

Contains

Hashgraph
Consensus
Libraries
Lockness

Handles

Keys

Digital Signatures

Trust Over IP

Creates standards

for digital trust.

Hyperledger Identus

Used for

Decentralized Identity (SSI).

Hyperledger Web3j

Java library

to interact with Ethereum.

Hyperledger AnonCreds

Anonymous credentials.

Maintains privacy.

Hyperledger Aries

Tools for digital identity.

Besu

Ethereum Client

written in Java.

Hyperledger Bevel

Framework

to simplify blockchain deployment.

Hyperledger Cacti

Connects multiple blockchains together.

Blockchain interoperability.

Hyperledger Caliper

Benchmark tool.

Measures blockchain performance.

Example

TPS

Latency

Hyperledger Cello

Blockchain as a Service.

Deploy blockchain easily.

Hyperledger Fabric

Enterprise blockchain framework.

Very popular.

Hyperledger FireFly

Platform

for enterprise Web3 applications.

Hyperledger Indy

Digital Identity blockchain.

Hyperledger Iroha

Blockchain for

Businesses

Financial institutions.

Solang

Solidity compiler

for Solana

and Substrate.

Hyperledger Fabric

Now the important topic.

What is Fabric?

Fabric is

An open-source

permissioned blockchain framework.

Originally created by

IBM

and

Digital Asset.

Why is Fabric popular?

Because it provides

✔ Privacy

✔ Identity

✔ Scalability

✔ Performance

✔ Smart Contracts

✔ Flexible Consensus

Biggest Advantage

Fabric was the first blockchain

allowing smart contracts

using normal programming languages.

Instead of Solidity

you can write

Go

JavaScript (Node.js)

Java

Much easier for developers.

Modular Architecture

Modular means

Everything can be changed independently.

Example

Like assembling a PC.

CPU

RAM

GPU

can all be changed.

Similarly

Fabric allows changing

Consensus

Identity

Database

etc.

Pluggable Consensus

Different companies

Different needs.

Fabric lets developers

change the consensus algorithm.

Examples

Raft

PBFT

SmartBFT

Identity Management

Unlike Bitcoin

Everyone is anonymous.

Fabric knows

exactly

who every participant is.

Uses

MSP

(Membership Service Provider)

Fabric Network Components

Your notes list six.

Let's learn one by one.

1. Peer

Peer = Computer (Node)

Stores blockchain copy.

Validates transactions.

Types of Peer
Committing Peer

Stores blocks.

Updates ledger.

Every peer is committing by default.

Endorsing Peer

Special peer.

Checks transaction.

Approves transaction.

Signs transaction.

This is called

Endorsement.

2. Orderer

Most important component.

Think of

Traffic Police.

Many cars arrive.

Traffic police

decides order.

Similarly

Orderer

collects transactions

↓

creates block

↓

sends block

↓

Peers store it.

Orderer never executes smart contracts.

Only orders transactions.

3. Client

Client is

Application used by users.

Example

Mobile app

Website

CLI

SDK

Client sends transaction requests.

4. MSP

Membership Service Provider.

Works like

College Administration.

Maintains

Student IDs.

Similarly

MSP manages

Identity

Certificates

Permissions.

5. Channels

One of Fabric's biggest features.

Imagine

One classroom.

Inside

Three groups.

Group A

cannot hear

Group B discussion.

Same classroom

Different conversations.

Channel works exactly like this.

Only channel members

see transactions.

Others cannot.

Think

Private WhatsApp Group.

6. Chaincode

Chaincode = Smart Contract.

Business logic lives here.

Example

Transfer money

Update asset

Delete asset

Everything written inside chaincode.

Hyperledger Fabric Lab

The lab shows how to run Fabric on Ubuntu.

Main steps:

Install prerequisites
curl
Docker
Docker Compose
jq
Build Essentials
Node.js & npm
Download Fabric samples.
Install Fabric binaries.
Start the test network.
Create a channel.
Deploy chaincode.
Set Org1 environment variables.
Initialize ledger (InitLedger).
Query all assets (GetAllAssets).
Read one asset (ReadAsset asset5).
Shut down the network (network.sh down).

You don't need to memorize every command unless you're doing the lab. Focus on understanding the purpose of each step.

Corda by R3

Now another permissioned blockchain.

What is Corda?

Corda is an enterprise distributed ledger platform developed by R3.

Main purpose:

Solve business problems

especially

Banks

Insurance

Finance.

Biggest Difference from Blockchain

Bitcoin

Transactions

↓

Grouped into Blocks.

Corda

No Blocks.

Each transaction

is verified

individually

in real time.

No waiting for block creation.

Features of Corda
Privacy

Only people involved

see transaction.

Others cannot.

Transaction Finality

Once approved

Transaction becomes final.

No multiple confirmations.

Legal Identity

Every node has

Real Identity

(X.500 Name).

No anonymous users.

Scalability

No blocks.

Processes transactions directly.

Therefore faster.

Enterprise Integration

Easy integration

with existing company systems.

Corda Components
CorDapp

Application

running on Corda.

Equivalent of DApp.

States

Represent current data.

Example

Owner of a car.

Contract

Rules.

Checks whether transaction is valid.

Commands

Tell contract

what action is happening.

Example

Transfer

Issue

Update

Attachments

Extra documents.

Example

PDF agreement

Legal document

Invoice.

Signatures

All participants sign.

Makes transaction immutable.

Notary

Very important.

Checks

No double spending.

Also

Adds timestamps.

PBFT (Practical Byzantine Fault Tolerance)

Consensus algorithm.

Created by

Barbara Liskov

Miguel Castro

(1999).

Used in permissioned blockchains.

Goal

Allow honest nodes

to agree

even if some nodes are malicious.

Advantages

✅ No mining

✅ Low electricity

✅ Fast

✅ Final transactions

Formula

Total Nodes = 3f + 1

where

f = Maximum faulty nodes.

Example

If

f = 1

Need

4 nodes.

If

f = 2

Need

7 nodes.

PBFT Phases
1. Pre-Prepare

Leader creates block.

Sends block to everyone.

Nodes perform initial checks.

2. Prepare

Every node sends

Prepare message.

Each node waits until it receives 2f + 1 matching prepare messages.

3. Commit

Nodes send

Commit messages.

Again, each node waits for 2f + 1 matching commit messages.

If enough commit messages are received,

the block is permanently added.

What if enough votes are NOT received?

Possible reasons:

Too many faulty nodes.
Leader is faulty.

Solution:

View Change

A new leader (primary) is elected, and the process starts again.

PBFT Variants
RBFT

Multiple PBFT instances run in parallel.

Used by Hyperledger Indy.

IBFT

Used in

Quorum

Hyperledger Besu.

SBFT

Improves PBFT.

Reduces communication cost.

Raft

Raft is another consensus algorithm.

Much simpler than PBFT.

It tolerates crashes (nodes failing) but does not tolerate malicious nodes.

Three Parts
Leader Election

One leader.

Others are followers.

If leader disappears,

Followers vote.

New leader elected.

Log Replication

Leader receives transactions.

Copies them

to followers.

Once majority agrees,

everyone stores them.

Safety

New leader

always contains

previous committed data.

No committed data is lost.

SmartBFT

SmartBFT is a Byzantine Fault Tolerant consensus mechanism used in Hyperledger Fabric.

It is based on the BFT-SMART protocol and is designed to work even if some nodes behave maliciously.

Main Components
Request Pool – Stores incoming transaction requests.
Block Assembler – Groups transactions into blocks.
Synchronization Mechanism – Keeps all nodes synchronized, even if some fall behind.
Advantages
Strong security.
Handles faulty or malicious nodes.
Protects against censorship.
Suitable for enterprise blockchains.
Disadvantage
Slower than Raft because extra communication is needed among nodes.
PART 1: Challenges or Opportunities?
First understand this...

Imagine you invented a new vehicle.

It is:

Faster than cars
Doesn't need petrol
Doesn't pollute

Sounds perfect, right?

But before everyone starts using it, there will be problems.

People may ask:

Is it safe?
Is it expensive?
Where can I charge it?
Can roads support it?

Blockchain is exactly like that.

Blockchain is powerful, but it still has many challenges.

Instead of seeing these as problems, we can see them as opportunities to improve the technology.

Blockchain challenges are divided into 3 categories

1. Technical Challenges
2. Organizational Challenges
3. General Challenges
PART 2: Technical Challenges

These are problems related to the technology itself.

Challenge 1: Scalability

This is one of the biggest blockchain problems.

What is Scalability?

Scalability means

Can the blockchain handle millions of users without becoming slow?

Example

Suppose only 10 people are standing in a queue.

Easy.

Now imagine

10 million people standing in the same queue.

Everything becomes slow.

That's blockchain today.

Why does blockchain become slow?

Because every transaction is verified by many nodes.

Example

Suppose Alice sends Bob ₹100.

Every full node checks

"Is Alice really sending ₹100?"

Thousands of computers verify this.

This gives security.

But it also makes the network slow.

Transaction Throughput

Throughput means

Number of transactions processed every second.

Also called

TPS (Transactions Per Second)

Example

Bitcoin

≈ 7 TPS

Meaning

Only about 7 transactions every second.

Ethereum

≈30 TPS

Visa

≈50,000 TPS

Imagine

Bitcoin

🚶
🚶
🚶

Visa

🚗🚗🚗🚗🚗🚗🚗🚗🚗🚗

Much faster.

Why can't Bitcoin become faster?

Because Bitcoin uses

Proof of Work

Every block takes around

10 minutes.

It is slow,

but very secure.

So blockchain has a trade-off.

More Security
↓

Less Speed

OR

More Speed

↓

Less Security
Storage Problem

Every blockchain node stores the complete blockchain.

Example

Blockchain size

500 GB

Every full node stores

500 GB.

If blockchain becomes

5 TB

Every node must store

5 TB.

Imagine

10,000 nodes

Each stores the same data.

Huge storage requirement.

Also

More transactions

↓

More blocks

↓

More storage

↓

Higher cost

Solutions to Scalability

The industry is working on many solutions.

Let's understand each one.

Solution 1: Better Consensus Algorithms

Instead of Proof of Work,

use

Proof of Stake
PBFT
Proof of Elapsed Time

These don't require solving difficult puzzles.

Advantages

✅ Faster

✅ Less electricity

✅ More TPS

Solution 2: Bigger Blocks

Current block

Suppose

1000 transactions

Increase block size

↓

Now

5000 transactions

fit into one block.

Example

Think of buses.

Small bus

20 passengers.

Large bus

80 passengers.

Fewer trips needed.

Bitcoin Cash uses larger blocks.

Solution 3: Sharding

One of Ethereum's biggest upgrades.

Imagine

School exam

1000 answer sheets.

Instead of one teacher correcting all,

10 teachers each correct

100 papers.

Work becomes much faster.

Blockchain does the same.

Instead of every node processing everything,

each node processes only one part.

These parts are called

Shards

Advantages

✅ Faster

✅ Less storage

✅ Better scalability

Solution 4: Off-chain Transactions

Instead of recording every small transaction,

people transact outside blockchain.

Only the final result goes onto blockchain.

Example

Rahul owes Karan

₹10

They exchange money 100 times.

Instead of recording all 100,

Blockchain records

Final balance.

Bitcoin Lightning Network works like this.

Ethereum uses

Raiden Network.

Solution 5: Sidechains

Imagine

Main highway

↓

Too much traffic.

Government creates

Service Road.

Some vehicles use the service road.

Traffic reduces.

Sidechains work similarly.

Main blockchain stays free.

Solution 6: DAG (Directed Acyclic Graph)

Traditional blockchain

Block
↓

Block
↓

Block
↓

Block

One after another.

DAG

No blocks.

Each transaction verifies other transactions.

Looks like

●──●──●
│  │
●──●──●

More transactions

↓

More validation

↓

Network becomes faster.

Example

IOTA uses DAG.

Challenge 2: Interoperability

Big word.

Simple meaning

Different blockchains cannot communicate.

Example

Imagine

Android phone

cannot send files to iPhone.

Very inconvenient.

Similarly

Bitcoin

cannot directly communicate

with Ethereum.

Solution

Projects like

Polkadot
Cosmos
Wanchain

try to connect different blockchains.

Think of them as

Universal translators.

Challenge 3

Lack of Skilled People

Blockchain is still new.

Not enough developers.

Solution

Train more blockchain engineers.

Exactly what you're doing now.

Challenge 4

Legacy System Integration

Companies already use

Old software.

Replacing everything

is difficult.

Need systems that connect

old software

with blockchain.

PART 3: Organizational Challenges

These are business-related problems.

1. Lack of Awareness

Many people think

Blockchain = Bitcoin

which is wrong.

Blockchain is much bigger.

Businesses don't understand it.

Therefore

they don't adopt it.

Solution

Education.

2. Non-compliance of Participants

Blockchain works only if everyone cooperates.

Example

Imagine

Group project.

5 students.

Only 2 work.

Project fails.

Permissioned blockchains especially require cooperation.

Solution

Rules

Policies

Governance

3. Security and Privacy

Public blockchain

Everyone can see transactions.

Businesses don't like that.

Example

Amazon doesn't want competitors seeing every sale.

Solution

Permissioned blockchain

Examples

Hyperledger Fabric
Corda

Only authorized people can view data.

4. Regulations

Governments haven't fully decided

Blockchain laws.

Questions include:

Is cryptocurrency legal?
How should taxes work?
Who is responsible if something goes wrong?

Organizations like IEEE are working on standards.

5. Return on Investment (ROI)

Businesses ask:

"If we spend ₹10 crore,

how much profit will we get?"

If blockchain doesn't improve business,

they won't use it.

Blockchain must provide real value.

PART 4: General Challenges

These affect everyone.

1. Bad Reputation

In the early days,

many scams used cryptocurrencies.

People started believing

Blockchain = Scam

Actually

Blockchain is only a technology.

Scammers misuse it,

just like scammers misuse email.

2. Environmental Impact

Bitcoin uses Proof of Work.

Mining consumes enormous electricity.

Solution

Move to

Proof of Stake

PBFT

RAFT

etc.

These consume much less energy.

3. Private Key Management

This is a very important challenge.

Normal banking

Forget password

↓

Reset password.

Blockchain

Lose Private Key

↓

Money is permanently lost.

No customer support.

No reset option.

Private key = Ownership.

PART 5: Current Trends

Now let's talk about blockchain's future.

Why are companies interested?

Because blockchain provides

✅ Trust

✅ Transparency

✅ Security

✅ No middlemen

Earlier

We trusted banks.

Now

People trust mathematics.

Blockchain uses cryptography instead of institutions.

Industries using Blockchain

Many industries are adopting blockchain:

Finance
Healthcare
Banking
Education
Agriculture
Government
Identity Management
Supply Chain

Example

Supply Chain

Farmer

↓

Factory

↓

Warehouse

↓

Shop

↓

Customer

Every step is recorded.

Nobody can secretly change records.

Smart Contracts

Old way

Paper agreement

↓

Lawyer

↓

Signatures

↓

Manual execution

Blockchain

Smart Contract

↓

Conditions met

↓

Automatically executes

No middleman.

Gartner Prediction

The material mentions that blockchain adoption is expected to grow over time:

2018–2021: Early excitement and experimentation.
2022–2026: More focused investments and successful business models.
2027–2030: Large-scale economic value from blockchain adoption.

The idea is that blockchain is expected to move from experimentation to widespread business use.

PART 6: Blockchain Applications

Blockchain is useful in many fields.

Examples include:

Finance
Banking
Healthcare
Supply Chain
Education
Agriculture
Identity Management
Government services

The reason is simple:

Whenever multiple parties need to share trusted data, blockchain can help.

PART 7: Token Economics

Now we move to a completely different topic.

What is a Token?

A token is simply

Something that represents value.

Example

Movie Ticket

Represents

One movie entry.

Restaurant Coupon

Represents

One meal.

Gift Card

Represents

Money.

Train Ticket

Represents

Travel permission.

These are all tokens.

Tokenization

Suppose you own a house worth ₹1 crore.

Instead of selling the entire house,

create

1000 digital tokens.

Each token represents

0.1% ownership.

People buy tokens instead of buying the whole house.

This process is called

Tokenization.

Token Economics

Token Economics studies:

How tokens are created.
How they are distributed.
How they are used.
How they gain value.
Tokens in Blockchain

On blockchain,

tokens represent digital value.

You can

Own them
Transfer them
Trade them
Program rules for them using smart contracts

Ethereum made tokens much more powerful by allowing programmable money.

Features of Crypto Tokens

A blockchain token has these features:

It digitally represents an asset.
It can represent tangible assets (gold, houses) or intangible assets (software licenses, loyalty points).
Ownership is recorded on the blockchain.
Ownership can be transferred through smart contracts.
Tokens can contain programmable rules.
Ownership records are immutable (cannot be changed).
Types of Tokens
1. Equity Token

Represents ownership in a company or asset.

Example:

Owning an equity token is similar to owning company shares.

If the company performs well, the token's value may increase.

2. Utility Token

Provides access to a service.

Example:

A gaming platform issues tokens that players use to buy in-game items.

It works like a prepaid coupon for that platform.

3. Security Token

Represents regulated financial assets.

These must follow government financial laws.

Example:

A token representing a regulated investment fund.

4. Asset Token

Represents a real-world asset.

Examples:

Gold
House
Bond

A gold-backed token has value because it is linked to real gold.

5. Currency Token

Works like digital money.

Example:

You use it to buy goods or services from merchants that accept it.

PART 8: NFT (Non-Fungible Token)
First understand "Fungible"

Fungible means:

One item can be exchanged for another identical item.

Example:

₹100 note

can be exchanged for

another ₹100 note.

Value remains the same.

Non-Fungible

Means

Unique.

Cannot be replaced with another identical item.

Examples:

Your birth certificate
Mona Lisa painting
Original artwork
Rare game item

Each is unique.

Why NFTs?

The digital world needs a way to prove:

Ownership
Scarcity (limited supply)
Authenticity (original item)

NFTs solve these problems.

Fungible vs Non-Fungible
Fungible	Non-Fungible
Interchangeable	Unique
Divisible	Usually treated as unique items
Same value	Value depends on uniqueness
Example: ₹100	Example: Original digital artwork
Ethereum Token Standards

To make tokens compatible, Ethereum defines standards.

ERC-20

Used for fungible tokens.

Example:

100 tokens of the same type are identical.

ERC-721

Used for NFTs.

Every token has a unique identity.

NFT Use Cases
1. Creator Economy

Artists can sell digital art directly and even receive royalties on future sales.

2. Gaming

Players truly own in-game items.

Example:

A rare sword can be bought, sold, or traded.

3. DeFi

NFTs can even be used as collateral for loans.

Fractional ownership also allows several people to own shares of an expensive NFT.

PART 9: DeFi (Decentralized Finance)
What is DeFi?

DeFi stands for

Decentralized Finance.

It means:

Traditional financial services are moved onto the blockchain.

Traditional Finance
You
↓

Bank
↓

Loan
↓

Interest

The bank controls everything.

DeFi
You
↓

Smart Contract
↓

Loan

No bank is required.

The smart contract automatically enforces the rules.

Why DeFi?

Traditional finance has limitations:

Some people cannot open bank accounts.
Banks may reject loans.
Services are available only during banking hours.
Middlemen increase costs.

DeFi aims to make financial services open to anyone with an internet connection.

Technologies Behind DeFi

DeFi combines:

Blockchain
Cryptography
Smart Contracts
Peer-to-Peer networking
Distributed Ledgers

Together they replace the role of traditional financial intermediaries.

Common DeFi Uses
Borrowing and Lending
Savings and Interest
Payments
Decentralized Exchanges (DEXs)
Insurance
Stablecoins
Investment products