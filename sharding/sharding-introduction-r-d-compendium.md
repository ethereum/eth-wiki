---
title: sharding-introduction-r-d-compendium
description: 
published: true
date: 2020-06-11T12:45:38.191Z
tags: 
---

# Sharding Introduction R&D Compendium

[![Documentation chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)
[![Sharding](https://img.shields.io/badge/gitter-sharding-4AB495.svg)](https://gitter.im/ethereum/sharding)

> Sharding+Casper/shasper with Ethereum 2.0 is the planned scaling approach for Ethereum; work is in progress on R&D.

Ethereum 1.0 can only process 7-15 transactions per second, the goal of sharding is to partition all network computational resources into shards, so that a node (a single computer as a peer connected to the network) doesn't have to process (download, compute, store, read) every transaction in the history of the blockchain, in order to make a new transaction (write and upload) or otherwise participate in securing and using Ethereum; rather a node can just participate in a single shard, or more if it so chooses. Multiple shards are handled separately by different subsets of securing participants, aka securitors (which include notaries, proposers, miners and validators)[\[1\]](https://eprint.iacr.org/2017/406.pdf). The primary goal is a massive scalability improvement, potentially exponential in phase 6 of the [roadmap](/sharding/sharding-roadmap.md); and probably at least a 100 fold increase in transactions per second with earlier phases. Quadratic sharding involves having shards at a depth of at most 1 from the main chain, that is, there are no shards within a shard, or a manager shard managing sub-shards; whereas exponential sharding has shards within shards, recursively.

Each one of the shards (likely 100 live in phase 1) will have as high a capacity (and likely more with phase 1) than the current existing Ethereum chain. A smart contract will exist on the main chain, called the sharding manager contract, which manages how data and transactions in shards are accepted as valid by the main chain, via notaries voting on the validity and data availability of collations (collections of data and transactions, analogous to blocks, but where they occur more frequently than blocks) in shards, and proposers proposing blobs (analogous to transactions but without execution in [phase 1](/sharding/sharding-roadmap.md)) which are collected into collations.

## Information

For information on sharding, refer to (sorted roughly from the most recent/important information to less recent):

-   sharding [roadmap](/sharding/sharding-roadmap.md) <!--leave this at the top of this list and maintain it-->
-   [Sharding FAQs](/sharding/Sharding-FAQs.md)
-   a summary [here](https://twitter.com/sinahab/status/992755776765792256);
-   [ethresear.ch sharding category](https://ethresear.ch/c/sharding) (watch new posts);
-   [sharding protocol research tracker](https://github.com/Drops-of-Diamond/diamond_drops/issues/13)
-   [Sharding Fork Choice rule PoC and more info, 2018 May 1](https://twitter.com/VitalikButerin/status/991021062811930624). Also see [here](https://github.com/Drops-of-Diamond/diamond_drops/issues/13) for an issue tracking protocol specification updates.
-   [Sharding introduction](https://docs.google.com/presentation/d/1mdmmgQlRFUvznq1jdmRwkwEyQB0YON5yAg4ArxtanE4/edit?usp=sharing)
    -   networking diagram on slides 82–87
-   [Sharding workshop notes](https://hackmd.io/s/HJ_BbgCFz#%E2%9F%A0-General-Introduction)
-   [Ethereum sharding workshop blog post](https://medium.com/@icebearhww/ethereum-sharding-workshop-in-taipei-a44c0db8b8d9)
-   [HackMD note: Ethereum Research Sharding Compendium](http://notes.ethereum.org/s/BJc_eGVFM)
-   [Wiki: ethresear.ch Sharding Compendium](/sharding/ethresearch-sharding-compendium.md)

## Implementations

Implementations under development include:

-   [sharding implementers call](https://github.com/ethresearch/eth2.0-pm)
-   [sharding utils](https://github.com/ethereum/sharding): has the sharding manager contract and interfaces.
-   py-evm/Trinity: [Gitter](https://gitter.im/ethereum/py-evm), [Github: sharding](https://github.com/ethereum/py-evm/tree/sharding), [Github: Trinity](https://github.com/ethereum/py-evm/tree/trinity). Trinity is the planned/under development EVM that will run a node and network.
-   Geth-sharding: [Github](https://github.com/prysmaticlabs/geth-sharding), [Gitter](https://gitter.im/prysmaticlabs/geth-sharding), [website](https://prysmaticlabs.com/).
-   [Drops of Diamond](https://github.com/Drops-of-Diamond/diamond_drops): using the fast, safe and concurrent [Rust](https://www.rust-lang.org/en-US/) programming language.
- [Lighthouse](https://github.com/sigp/lighthouse): implemented the first version of the shasper spec, while work is still underway while waiting for the latest spec to finalize.
-   Nimbus ([doc](https://docs.google.com/document/d/14u65XVNLOd83cq3t7wNC9UPweZ6kPWvmXwRTWWn0diQ/edit#)): an implementation in Nim which compiles to C, and would be good for integrating with [Hera](https://github.com/ewasm/hera), an eWASM implementation in C++. Developed by Status, they are looking to support mobile phones.
-   [Artemis](https://github.com/PegaSysEng/artemis) [PegaSys](https://twitter.com/PegasysEng) [ConsenSys](https://consensys.net): Java Implementation of the Ethereum 2.0 Beacon Chain
-   [Lodestar](https://github.com/ChainSafeSystems/lodestar_chain) [ChainSafe Systems](https://chainsafe.io): an implementation of the beacon chain in JavaScript.
-   [Shasper](https://github.com/paritytech/shasper) [Parity Technologies](https://parity.io): Shasper beacon chain implementation using the Substrate framework.
- deprecated: [sharding utils](https://github.com/ethereum/sharding): has the sharding manager contract and interfaces.

## Grant program

-   <https://blog.ethereum.org/2018/01/02/ethereum-scalability-research-development-subsidy-programs/>
-   <https://github.com/Drops-of-Diamond/diamond_drops/issues/18>

## Alternative scaling approaches to sharding

-   Moved to [here](/research/alternative-blockchains-randomness-economics-and-other-research-topics.md).
-   For precursor research scaling ideas, see para 2. [here](https://vitalik.ca/2017-09-15-prehistory.html) (see the links to hypercubes and [Chain Fibers](/scalability/chain-fibers-redux.md)—a precursor to [sharding](/sharding/sharding-introduction-r-d-compendium.md), as well as hub-and-spoke chains). - 
-   [Scaling proposals](https://github.com/jpitts/eth-community-discussions/blob/master/proposals-to-scale.md)

## Glossary

Enshrined-in-consensus: see <https://ethresear.ch/t/sharding-phase-1-spec-retired/1407/18>.
