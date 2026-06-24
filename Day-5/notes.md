1. Why Ethereum was created?
Problem with Bitcoin

Bitcoin was mainly designed for sending and receiving money.

Vitalik Buterin thought:

"Why not create a blockchain where people can build any application, not just send money?"

So he proposed Ethereum in 2013.

Bitcoin Limitations Mentioned by Vitalik
1. Lack of Turing Completeness

Bitcoin scripting language is limited.

❌ Cannot build complex applications.

Example:

Online voting app
Supply chain app
NFT marketplace

Ethereum supports these.

2. Value Blindness

Bitcoin uses UTXO.

Example:

You have 5 BTC.

Need to send 3 BTC.

You must:

Send 5 BTC
Receive 2 BTC back as change

This creates extra complexity.

Ethereum uses account balances directly.

3. Lack of State

Bitcoin only knows:

Spent
Unspent

Ethereum can maintain many states.

Example:

Food order app

States:

Ordered
Preparing
Out for delivery
Delivered
4. Blockchain Blindness

Bitcoin cannot easily use blockchain data for advanced applications.

Ethereum can.

2. Ethereum World Computer

Ethereum's vision:

One giant decentralized computer shared by the whole world.

Properties:

Deterministic

Same input = same output everywhere.

Example:

2 + 2 = 4

Every Ethereum node gets same answer.

Terminable

Programs can be stopped.

Prevents infinite loops.

Isolated

Programs run safely.

One application cannot damage another.

3. Ethereum Virtual Machine (EVM)
What is EVM?

EVM = Ethereum Virtual Machine

It executes smart contracts.

Think:

Computer → Runs programs

Ethereum → EVM runs smart contracts

Why EVM?

Provides a common environment.

No matter:

Windows
Linux
Mac

All nodes execute contracts identically.

4. Ethereum Features
Adaptable & Flexible

Developers can build:

Games
Banking apps
Voting systems
NFTs
User Authentication

Uses:

Public Key
Private Key
Digital Signature

to verify users.

Easy Payment Logic

Money transfer logic can be coded directly.

DDoS Resistance

No central server.

Therefore difficult to attack.

Interoperability

Smart contracts can communicate with other smart contracts.

No Server Infrastructure

Peer-to-peer network.

No central authority.

5. Why Ethereum moved from PoW to PoS?

Problems in PoW:

Huge electricity consumption
Expensive hardware
Scalability issues

Solution:

Proof of Stake (PoS)

6. Proof of Stake (PoS)

Instead of mining power,

validators are selected based on staked coins.

Validators

Validators replace miners.

Responsibilities:

Validate transactions
Create blocks

Reward:

Receive ETH rewards.

Punishment (Slashing)

If validator cheats:

Invalid transactions
Double signing

Part of stake is removed.

7. Why PoS is safer?

PoW attack:

Need 51% computing power.

PoS attack:

Need 51% ETH.

Very expensive.

Also attacker would lose value of his own holdings.

8. Validator Selection Methods
A. Randomized Selection

Uses:

Stake
Randomness

to choose validator.

B. Coin Age Selection

Coin Age =

Coins × Days Held

Example:

10 coins × 20 days

= 200 coin-age

Higher coin-age gets better chance.

9. Ethereum's Current Validator Selection

Uses:

RANDAO

Pseudo-random mechanism.

Epoch

Time block.

1 Epoch = 32 Slots

Slot

1 Slot = 12 seconds

Each slot has:

One Block Proposer
Validator Committee
Committee

Group of validators.

Minimum around 128 validators.

They vote on blocks.

10. Advantages of PoS
Energy Efficient

No heavy mining.

Randomization

Reduces centralization.

More Secure

Attacks become expensive.

11. Nothing-at-Stake Problem

In PoW:

Miner can mine only one chain.

In PoS:

Validator can vote on multiple chains.

No extra cost.

Could earn rewards regardless.

This is called:

Nothing-at-Stake

Solution:

Punish validators (slashing).

12. Variants of PoS
Delegated PoS
Liquid PoS
Bonded PoS
Hybrid PoS

Just remember names.

13. Proof of Authority (PoA)

Used mainly in private blockchains.

Validators are chosen by:

Reputation

not coins.

Example:

Trusted companies validate blocks.

Requirements
Trusted Identity

Validators must be known.

Reputation Risk

Their reputation is at stake.

Fair Selection

All validators should have equal opportunity.

Advantages
Fast

Few validators.

Highly Scalable

Handles many transactions.

Good for Supply Chains

Private business networks.

Privacy

Sensitive data can remain private.

No Mining

No native token required.

Disadvantages
Centralized

Few validators control system.

Censorship Possible

Validators may block users.

Third-party Manipulation

More possible than public chains.

14. Ethereum Evolution Roadmap

Ethereum continuously upgrades.

Beacon Chain

Launched in 2020.

Purpose:

Run PoS separately.

Validators stake:

32 ETH

each.

The Merge (2022)

Main Ethereum chain joined Beacon Chain.

Result:

Ethereum switched from:

PoW → PoS

Huge Benefit

Energy consumption reduced by:

~99.95%

15. Dencun Upgrade

Original plan:

64 Shard Chains

to split workload.

Later replaced by:

Proto-Danksharding

Helps Layer-2 networks store data cheaply.

Benefits:

Lower fees
Better scalability
16. Ethereum Accounts

Two types.

Externally Owned Account (EOA)

Controlled by user.

Example:

MetaMask account.

Features:

Controlled by private key
No smart contract
Free to create
Contract Account

Controlled by smart contract.

Features:

Has code
Executes automatically
Costs gas to deploy
Both Can
Hold ETH
Send ETH
Receive ETH
Interact with contracts
17. Ether (ETH)

Native currency of Ethereum.

Used for:

Payments
Gas fees
Denominations

Smallest unit:

Wei

1 ETH = 10¹⁸ Wei

Important units:

Wei
Gwei
Ether
Gwei

Most gas fees are expressed in Gwei.

18. Gas

Gas measures computational work.

Think:

Electricity → Kilowatt

Ethereum → Gas

Every operation has a gas cost.

Examples:

Transfer ETH
Run contract
Store data
19. Why Gas Exists?
Prevent Spam

Attackers must pay.

Prevent Infinite Loops

When gas finishes:

Program stops.

This ensures Ethereum is terminable.

20. Old Fee Formula

Transaction Fee

= Gas Limit × Gas Price

Gas Limit

Maximum gas user allows.

Example:

21000 gas for ETH transfer.

Gas Price

Price per gas unit.

21. New Fee Formula (London Upgrade)

Transaction Fee

= Gas Limit × (Base Fee + Tip)

Base Fee

Mandatory fee.

Burned permanently.

Tip

Extra reward for validators.

Result

More predictable fees.

ETH becomes partially deflationary because base fees are burned.

22. Account Balance Model

Ethereum uses:

Account Balance Model

instead of UTXO.

Example:

Hari = 100 ETH

Send 20 ETH

New Balance = 80 ETH

Simple.

Benefits
Simpler

Easy for developers.

Efficient

Only check sender balance.

No UTXO tracking.

23. Ethereum Nodes

A node is a computer connected to Ethereum.

Full Node

Stores entire blockchain.

Validates blocks.

Light Node

Stores only headers.

Downloads data when needed.

Uses Merkle Proofs.

Archive Node

Stores:

Entire blockchain
Entire history of all states

Used by:

Explorers
Wallets
Analytics platforms
24. Ethereum Networks
Mainnet

Real Ethereum network.

Real ETH.

Network ID = 1

Beacon Chain

PoS coordination chain.

Launched before Merge.

25. Testnets

Used for testing.

ETH has no real value.

Obtained through faucets.

Sepolia

Current preferred developer testnet.

Network ID:

11155111

Goerli

Older testnet.

Now deprecated.

Network ID:

5

Holesky

Successor to Goerli.

Used mainly for staking and infrastructure testing.

26. Ethereum Clients

Software that runs Ethereum nodes.

Execution Clients

Handle:

Transactions
EVM execution
Storage

Examples:

Geth
Hyperledger Besu
Erigon
Nethermind
Consensus Clients

Handle PoS consensus.

Examples:

Prysm
Teku
Lighthouse
Nimbus
27. Blockchain Simulation Tools

Used by developers.

Ganache

Local blockchain simulator.

Remix VM

Runs blockchain inside browser.

Hardhat Node

Testing environment.

28. DApps (Decentralized Applications)

A DApp is an application that interacts with blockchain.

Examples:

NFT marketplace
Voting app
DeFi app
DApp Architecture (5 Layers)
1. Front End

User interface.

Examples:

Buttons
Forms
Web pages
2. Web3 Layer

Libraries connecting frontend to Ethereum.

Examples:

Web3.js
Ethers.js
3. Smart Contract

Business logic.

Example:

"Transfer money if conditions are met."

4. Ethereum Virtual Machine (EVM)

Executes smart contracts.

5. Operating System

Windows/Linux/Mac machine running EVM.