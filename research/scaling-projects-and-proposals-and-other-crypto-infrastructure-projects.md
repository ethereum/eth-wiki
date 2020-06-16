---
title: Scaling projects and proposals and other crypto infrastructure projects
description: 
published: true
date: 2020-06-16T09:23:26.328Z
tags: 
---

# Scaling projects and proposals and other crypto infrastructure projects


Of all the crypto projects I've looked into so far, including Ethereum, [Holochain](https://holochain.org/) appears to be the most useful.

See also [these scaling proposals](https://github.com/jpitts/eth-community-discussions/blob/master/proposals-to-scale.md).

Alternative approaches to scaling other than sharding include state channels, side chains, multi-chains and off-chain computation. Projects are included [here in this summary spreadsheet by the Web3 Foundation](https://docs.google.com/spreadsheets/d/1BQ0bK_LhSQvxtvXryVoIcmxeKMuVJCq6oD0aS5_hpC8). [Parity Substrate](https://www.reddit.com/r/ethereum/comments/8dgoup/parity_substrate/) is another project. Other designs and sources of inspiration include:
- [projects related to relaying transactions](https://github.com/ethereum/wiki/wiki/Relay-projects)
- [storage incentivization projects](https://github.com/ethereum/wiki/wiki/Storage-projects)
- [Dfinity](https://www.dfinity.org/pdf-viewer/pdfs/viewer?file=../library/dfinity-consensus.pdf), uses a random beacon chain and notaries, which Ethereum plans to implement, although the randomness source may be [RANDAO](https://github.com/ethereum/research/blob/master/sharding_fork_choice_poc/beacon_chain_node.py) instead of BLS aggregate signatures.
- [Truebit](https://truebit.io/) interactive verification off-chain protocol for Ethereum.

Potential sources of inspiration / other projects include:
- [PHANTOM and SPECTRE, alternative DAG designs](https://ethresear.ch/t/phantom-and-spectre-by-a-zohar-and-y-sompolinsky/1888)
- [Cardano](https://cardanodocs.com/introduction/): uses [sidechains](https://www.blockstream.com/sidechains.pdf) for scaling
- [Algorand](https://www.algorand.com/whitepapers/)
- [OmniLedger](https://eprint.iacr.org/2017/406.pdf)
- [RChain](http://architecture-docs.readthedocs.io/introduction/motivation.html): aims to support scalable, mission-critical projects, without enforcing a strict total order on all transactions in the blockchain (which poses problems around consensus, double-spending, etc.)
- plus a lot more inspiration from research literature.

## Team Rocket with Snowflake to Avalanche

[Snowflake to Avalanche: A Novel Metastable Consensus Protocol Family for
Cryptocurrencies](https://ipfs.io/ipfs/QmUy4jh5mGNZvLkjies1RWM4YuvJh5o2FYopNPVYwrRVGV): it's a probabilistic Byzantine fault tolerant (BFT) consensus protocol that is synchronous on paper, but has been developed on a real internet (which is partially synchronous at best).

## Ziliqa

[Ziliqa](https://docs.zilliqa.com/whitepaper.pdf): a PoW sharded architecture consisting of a dataflow smart contract layer, and 5 other layers. Uses the EC-Schnorr multiginature signature scheme. However, RANDAO is preferable to aggregate/multisignature schemes since it is not prone to a 51% attack. Also uses committees, as is planned with Dfinity and Ethereum, although here the committees manage how miners are assigned to shards, whereas in Ethereum that is the task of the beacon chain and the sharding manager contract on the main chain. Uses PBFT consensus, which doesn't seem to be as good as [Casper](https://github.com/ethereum/wiki/wiki/Casper-Proof-of-Stake-compendium) [FFG](https://eips.ethereum.org/EIPS/eip-1011), which is also used with PoW.

## EOS

[EOS](https://eos.io/): has a DPOS (delegated proof of stake) protocol. It experienced a liveness fault [[1]](https://www.coindesk.com/cold-reception-crypto-reacted-eos-blockchain-freeze/) and locked accounts to prevent theft just days after launch (which has spillover effects to other cryptocurrencies if exchanges decide to socialize losses from EOS, e.g. by freezing accounts of EOS and other cryptocurrencies and declaring bankruptcy, which in turn has legal implications [[2]](https://www.coindesk.com/eos-locked-7-accounts-implications-everyone-crypto/)). It is controlled by a relatively centralised server and cartel of 21 block producers. It does not have a provably correct-by-construction, formally verified consensus protocol. It is very expensive with deposits instead of fees (deploying Cryptokitties on it at it's peak would cost about $1.5b in staked deposits) [[3](https://ethresear.ch/t/against-replacing-transaction-fees-with-deposits/940/3), [4](https://ethresear.ch/t/against-replacing-transaction-fees-with-deposits/940?u=jamesray1)]. You need to pay to create an account, need EOS to buy RAM in order to make transactions. Need to stake EOS for CPU and network resources (IMO this is a necessary con, since without incentivizing resource use, a tragedy of the commons arises; see e.g https://eips.ethereum.org/EIPS/eip-908).

## Bitcoin and Bitcoin Cash

Both lack a Turing complete language to use for stored procedures (more commonly known by the less appropriate name of smart contract) and decentralised apps (dapps)

Regarding Bitcoin Cash, doubling the block limit does not seem like a good idea, as it makes the network more centralized. The roadmap also includes "adaptive block size (market driven growth to 1 TB). Again this is not good for decentralization and security. It's uncertain how Bitcoin Cash and Bitcoin are going to be sustainable by having low rewards and high fees (and no gas limit, which is not good for pricing economics; FMI see DRAFT: Position paper on resource pricing (https://ethresear.ch/t/draft-position-paper-on-resource-pricing/2838)). Both will continue to use PoW which is bad for scaling, energy consumption, decentralization and security. Bitcoin using Lightning Network isn't sustainable long-term (like other L2 solutions); FMI see ethereum/wiki (https://github.com/ethereum/wiki/wiki/Sharding-FAQs#how-does-plasma-state-channels-and-other-layer-2-technologies-fit-into-the-trilemma).

## Early research
For precursor research scaling ideas, see para 2. [here](https://vitalik.ca/2017-09-15-prehistory.html) (see the links to hypercubes and [Chain Fibers](https://github.com/ethereum/wiki/wiki/Chain-Fibers-Redux)—a precursor to [sharding](https://github.com/ethereum/wiki/wiki/Sharding-introduction-R&D-compendium), as well as hub-and-spoke chains).