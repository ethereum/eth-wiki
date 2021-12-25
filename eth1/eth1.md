---
title: Ethereum 1x
description: 
published: true
date: 2019-07-23T02:26:41.266Z
tags: 
---

This is the current "version" of Ethereum. [EthHub has extensive information and background on ETH1x](https://docs.ethhub.io/ethereum-roadmap/ethereum-1.x/).

You may also want to review the [roadmap](/roadmap/roadmap.md).
# Working Groups
A list of current working groups focused on core research, upgrades, and challenges.

## State Rent
Implementing state rent to address large and growing state. State rent is only one solution, so other facets are explored too - advanced snapshot sync algorithms, stateless clients, etc.

* Leads: Alexey Akhunov

## Finality Gadget
Using the ETH2 beacon chain to finalize ETH1 blocks.

* Leads: ?
* Alexey's [presentation slides](https://drive.google.com/open?id=16KLZKAutK79NxMh8L7B6hpNKuoOaAPZT) and [video](https://youtu.be/HaT-BIzWSew?t=24502)
* EthMagicians Thread https://ethereum-magicians.org/t/finality-gadget-for-ethereum1x-working-group/3177

Alexey is interested in seeing this happen, but doesn't have the bandwidth to lead this Working Group. Please comment in the EthMagicians thread if you want to get involved.

## Generalised precompile for Elliptic Curve arithmetics and pairings
Discussion groups for at least one proposal (e.g. [elliptic curve linear combinations](https://ethereum-magicians.org/t/precompile-for-general-elliptic-curve-linear-combinations/2581)).
* Leads: Alexander Vlasov
* EthMagicians Thead [group formation](https://ethereum-magicians.org/t/generalised-precompile-for-elliptic-curve-arithmetics-and-pairings-working-group/3208)
* EthResearch Thread [group formation](https://ethresear.ch/t/generalised-precompile-for-elliptic-curve-arithmetics-and-pairings-working-group/5370)

## Ewasm
Building a spec for Ethereum-flavoured WebAssembly (wasm) and determining what might go into ETH1x vs. preparing for ETH2.

_Note: there are people working at the EF working on this, but there is no plan of record or list of EIPs. Related to some of the EVM Evolution work._

## EVM Evolution

Improvements to the current EVM around speed, safety, and interoperability. Safety improvements will increase the capabilities of static analysis and formal verification tools operating on EVM. Interoperability improvements include making EVM a better code generation target for higher-level languages like Solidity and Vyper, as well as lower-level bytecode formats such as WebAssembly/Ewasm and LLVM IR. Also helping form long-term plans for EVM across the ETH1x and ETH2 roadmaps.

* Leads: 

### EIPs

* EIP 615 (withdrawn)
* VM Versioning by @sorpaas is needed for both 615 and eWASM

_Note: currently unfunded, so leads Brooke Zelenka & Greg Colvin have stepped away from core Ethereum work_

## Fee Market change
Also known as EIP-1559, splitting gas fees that transactions are paying into two parts. One part gets burnt (destroyed), another - paid to the miners. In theory, this should make total transaction fees more stable and predictable.
* Leads: Rick Dudley
* Vitalik's [presentation slides](https://drive.google.com/open?id=12bCGHxv9uldSvh-dcDS5qc53XqZDOOHD) and [video](https://www.youtube.com/watch?v=HaT-BIzWSew&t=4706s)
* EthMagicians Threads: [prior discussion](https://ethereum-magicians.org/t/eip-1559-fee-market-change-for-eth-1-0-chain/2783) [group formation](https://ethereum-magicians.org/t/fee-market-change-working-group-formation-and-my-proposed-amendment/3195)
* EthResearch Threads: [group formation](https://ethresear.ch/t/fee-market-change-working-group-formation-and-my-proposed-amendment/5365)

# Initiatives
Smaller initiatives around core systems and processes, calls for collaboration.

## Hardfork Cadence

* Leads: Danno
* See https://ethereum-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28

# Infrastructure
Ongoing infrastructure focus areas for coordinating work & support on the core network.

## Testing
* Leads: Zak, Dmitry, wtf

### Consensus Testing

* Leads: Dmitry

# Meetings
* July 2019?
* April 17-18th, 2019 [Core Devs Berlin](/eth1/coredevsberlin.md) - feedback and poll on July meeting https://ethereum-magicians.org/t/coredevs-eth1x-istanbul-meeting-july-poll-feedback/3197
* February 2020 ETH1x Roadmap AMA [notes & video on EthMagicians](https://ethereum-magicians.org/t/eth-roadmap-ama-webinar-feb-6th-8am-pst-1700-utc-1/2518)
