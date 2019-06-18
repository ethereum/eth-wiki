---
title: Istanbul
description: October 2019 Planned Ethereum Network Upgrade
published: true
date: 2019-06-18T07:09:57.047Z
tags: 
---

The [ETH1](/eth1) page is a good starting point for an overview of Working Groups and areas of focus.
# Timelines
* 2019-04-17 (Wed-Thurs) CoreDev planning meeting in Berlin, [details on EthMagicians](https://ethereum-magicians.org/t/istanbul-eth1x-roadmap-planning-meeting-april-17th-18th-in-berlin/2899)
* 2019-05-17 (Fri) hard deadline to accept proposals for “Istanbul”
* 2019-07-19 (Fri) soft deadline for major client implementations
* 2019-07 CoreDev planning meeting proposed
* 2019-08-14 (Wed) projected date for testnet network upgrade (Ropsten, Görli, or ad-hoc testnet)
* 2019-10-8 - 11 DevCon5 Osaka Japan
* 2019-10-16 (Wed) projected date for mainnet upgrade (“Istanbul”)

Rough plan is April 2020 for next Hardfork, go up to [Roadmap](/roadmap) for more info.

# Proposals
Discussion thread for Hardfork Meta: https://ethereum-magicians.org/t/hardfork-meta-istanbul-discussion/3207

**The list of [EIPs in 1679](https://eips.ethereum.org/EIPS/eip-1679) are the canonical status of EIPs**

This will be maintained as an overview page, can also view the [Istanbul GitHub Project in the ECH repo](https://github.com/orgs/ethereum-cat-herders/projects/2) to track progress.

James Hancock has created an [automated Google Sheet that covers additional milestones](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0)


## Proposed

The deadline for EIP proposals for Istanbul was May 17th. All of these EIPs intend to prepare for inclusion in Istanbul, but Core Dev acceptance, implementation, testing, audits, and other work needs to be done to prepare them. Each EIP has a "discussion-to" link where you can find more information, usually on the [EthMagicians Core EIPs forum](https://ethereum-magicians.org/c/eips/core-eips).

* [EIP 615](https://eips.ethereum.org/EIPS/eip-615): Subroutines and Static Jumps for the EVM
* [EIP 1057](https://eips.ethereum.org/EIPS/eip-1057): ProgPoW, a Programmatic Proof-of-Work (contingent on positive audit results) - @IfDefElse
* [EIP 1108](https://eips.ethereum.org/EIPS/eip-1108): Reduce alt_bn128 precompile gas costs - @zac-williamson
* [EIP 1283](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1283.md): Net gas metering for SSTORE without dirty maps @sorpass
* [EIP 1344](https://eips.ethereum.org/EIPS/eip-1344): Add ChainID opcode - @fubuloubu
* [EIP 1352](https://eips.ethereum.org/EIPS/eip-1352): Specify restricted address range for precompiles/system contracts
* [EIP 1380](https://eips.ethereum.org/EIPS/eip-1380): Reduced gas cost for call to self - @axic @jacqueswww
* [EIP 1559](https://eips.ethereum.org/EIPS/eip-1559): Fee market change for ETH 1.0 chain
* [EIP 1965](https://eips.ethereum.org/EIPS/eip-1965): Method to check if a chainID is valid at a specific block Number
* [EIP 1702](https://eips.ethereum.org/EIPS/eip-1702): Generalized account versioning scheme - @sorpaas
* [EIP 1706](https://eips.ethereum.org/EIPS/eip-1706): Disable SSTORE with gasleft lower than call stipend
* [EIP 1803](https://eips.ethereum.org/EIPS/eip-1803): Rename opcodes for clarity - @axic
* [EIP 1829](https://eips.ethereum.org/EIPS/eip-1829): Precompile for Elliptic Curve Linear Combinations @remco
* [EIP 1884](https://github.com/ethereum/EIPs/blob/dcc573e74adc0e6dd25821ddaabf862e8f85e107/EIPS/eip-1884.md): Reprice Opcodes + optional new opcode, @holiman - [Discuss](https://ethereum-magicians.org/t/opcode-repricing/3024)
* [EIP 1930](https://eips.ethereum.org/EIPS/eip-1930): CALLs with strict gas semantic. Revert if not enough gas available
* [EIP 2028](https://eips.ethereum.org/EIPS/eip-2028): Calldata gas cost reduction


_Follow along All Core Dev calls and the [EIPs repo](https://github.com/ethereum/EIPs)._

----

### EIP AMAs on All Core Devs Gitter

To reduce the load on discussing each EIP in the dev calls, some EIP coordination can happen in the [AllCoreDevs gitter](https://gitter.im/ethereum/AllCoreDevs). 

Future planned AMA dates: None

Previous AMA dates for reference:

**Elliptic curve cluster**: Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Account versioning cluster**: Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Chain metadata cluster**: Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Storage gas cost cluster**: Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Storage writing cluster** Fri 7th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Live All Core Devs Call**: 
- For EIPs people feel are maturing enough to be considered for acceptance into Istanbul should add a comment to [21 June All Core Devs Call Agenda](https://github.com/ethereum/pm/issues/102) with a note about intention (e.g. I intend to briefly present EIP xyz for consideration for acceptance into Istanbul). 
- Call attendees can then read up on the EIP beforehand so that decisions can be made effectively during the call.
- Attending the call to present your EIP goes a long way to getting the change included in Istanbul.
- Next steps for EIPs are to communicate plans for a reference client implementation and plans for testing. If additional resources are needed to achieve those, make that known either in the EIP, in the discussions-to forum, or here in the table under **step required** so that interested parties can get involved.

<img src="https://docs.google.com/drawings/d/e/2PACX-1vS7t5kwTrxL3zja2hLIPcNchPtBoXBeSxWNG8-tm5vlGPV4XycY7PMQDWKQGRXd_vwEPLO8dIbPR7EH/pub?w=2762&amp;h=1430">

[Link to Google Drawing](https://docs.google.com/drawings/d/14vSgSGLkr9iPLTpOuZrtSoGyspHYDPh9ue6Ki4hrj54/)

### Roadblock Spotter

Below is a one-glance table to summarise the current roadblock for each EIP. The table serves to remind what has been most recently discussed in various channels, including All Core Dev Calls. If a roadblock has been addressed, feel free to remove it from the table. If there are concerns about the suitability of an EIP or its fitness for consideration, please add a note here, but take discussions to the the forum listed in the individual EIP. 'Checkpoint issues', such as and EIP not yet having a major client implementation or not having yet submitted test cases are considered 'standard preparations', which are [tracked](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0) for each EIP and are not included below.


<div align="center">

| Cluster | EIP (strike == not for istanbul)  | Any [non-checkpoint](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0) issue preventing suitability for Istanbul? 	| Planned AMA or ACD call date 	| Step required	|
|---	|--- |---	|---	|---	|---	|
| **Account versioning** | [615](https://eips.ethereum.org/EIPS/eip-615) Subroutines and Static Jumps for the EVM	| Authoring team (mainly Greg Colvin) may need volunteers to help generate tests or implementations. | None planned	| Volunteers interested in seeing this EIP succeed (e.g. Feist from Trail of Bits?) could reach out to Greg to offer a hand  |
| **Account versioning** | ~~[663](https://eips.ethereum.org/EIPS/eip-663) Unlimited SWAP and DUP instructions~~	| [Solves the same](https://youtu.be/lF_XxqxgVuA?t=1934) stack-access problem as 615, which is likely going ahead. Additionally, three technical options are presented and would need to be refined. 	| None planned	| If 615 is cancelled, 663 may be desired. If so, select one of the three options.	|
| - | ~~[689](https://eips.ethereum.org/EIPS/eip-689) Address Collision of Contract Address Causes Exceptional Halt~~	| [Not needed](https://youtu.be/lF_XxqxgVuA?t=283). No hard fork required and is covered by [issue 684](https://github.com/ethereum/EIPs/issues/684) 	| None planned | Non-istanbul client implementations	|
| - | [1057](https://eips.ethereum.org/EIPS/eip-1057) ProgPoW, a Programmatic Proof-of-Work	| Audit may find hardward/software issues. Danno notes that [a small addition is required](https://ethereum-magicians.org/t/eip-progpow-a-programmatic-proof-of-work/272/13) 	| None planned	| Danno Ferrin to implement addition. Work on client implementations as if will go in. If audit happens and issue found, may need to delay to April hard fork. 	|
| **Elliptic curve** | [1108](https://eips.ethereum.org/EIPS/eip-1108) Reduce alt_bn128 precompile gas costs	| Benchmarks [incomplete](https://youtu.be/lF_XxqxgVuA?t=2896) 	| None planned	| Zachary Williamson to re-run benchmarks. Mariano Conti [is offering help if needed](https://twitter.com/nanexcool/status/1134583012748869634) 	|
| **Elliptic curve** | [1109](https://eips.ethereum.org/EIPS/eip-1109) PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)	| 2046 conflicts with 1109. 	| Jordi Baylina will attend [21 June All Core Devs Call](https://github.com/ethereum/pm/issues/102) to support 1109	| Alex Beregszaszi (2046), Jordi Baylina (1109) and **elliptic curve** stakeholders need to [discuss](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447) |
| **Storage writing** | [1283](https://eips.ethereum.org/EIPS/eip-1283) Net gas metering for SSTORE without dirty maps	| None 	| None planned	| -	|
| **Chain metadata** | [1344](https://eips.ethereum.org/EIPS/eip-1344) ChainID opcode	| Can co-exist with 1965, which provides similar but complementary function | None planned	| Any final concerns that this should not co-exist with 1965 should be directed to the [forum](https://ethereum-magicians.org/t/eip-1344-add-chain-id-opcode/1131/93)	|
| - | [1352](https://eips.ethereum.org/EIPS/eip-1352) Specify restricted address range for precompiles/system contracts	| No consensus on whether precompiles should be addressed via a range (1352) or by client-based-lists | None planned	| Anyone interested in seeing this go ahead should make their case [here](https://ethereum-magicians.org/t/eip-1352-restricted-address-range-for-precompiles-system-contracts/1151)	|
| - | [1380](https://eips.ethereum.org/EIPS/eip-1380) Reduced gas cost for call to self	| Not yet discussed in gitter AMA or dev call. EIP title needs to be [clearer](https://github.com/ethereum/EIPs/pull/1803/#issuecomment-488119162) 	| None planned	| Update EIP title 	|
| - | [1559](https://eips.ethereum.org/EIPS/eip-1559) Fee market change for ETH 1.0 chain	| Péter Szilágyi: [May effect transaction propagation](https://youtu.be/lF_XxqxgVuA?t=4506) Rick Dudley: EIP may not be completed in time 	| None planned	| Rick Dudley to work toward Istanbul and make patch for network propagation 	|
| **Account versioning** | [1702](https://eips.ethereum.org/EIPS/eip-1702) Generalized Account Versioning Scheme	| Rough consensus has formed around Design-2 (with code prefix). No issues unless there is strong preference for Design-1 (no prefix) 	| None planned	| Those strongly opposed to this EIP or Design-2 (with prefix) should raise issues in the main discussions-to thread |
| **Storage writing** | [1706](https**://eips.ethereum.org/EIPS/eip-1706) Disable SSTORE with gasleft lower than call stipend	| May not be needed for 1283 (because account versioning progressing well), but may still be benificial for future changes	| None planned	| Interested parties to review the parity [implementation](paritytech/parity-ethereum#10191)	|
| **Account versioning** | ~~[1707 PR](https://github.com/ethereum/EIPs/pull/1707) Use Version Byte Prefix for Contract Account Versioning~~ | Not needed, given 1702 progressing. 	| None planned	| -	|
| **Account versioning** | ~~[1712 PR](https://github.com/ethereum/EIPs/pull/1712) Disallow Deployment of Unused Opcodes~~	| Not needed, given 1702 progressing. 	| None planned	|  -	|
| - | [1803](https://eips.ethereum.org/EIPS/eip-1803) Rename opcodes for clarity	| Not yet discussed in gitter AMA or dev call 	| None planned	|  	|
| **Elliptic curve** | ~~[1829](https://eips.ethereum.org/EIPS/eip-1829) Precompile for Elliptic Curve Linear Combinations~~	| Not needed, given 1962 progressing. 	| None planned	| - |
| - | [1848 PR](https://github.com/ethereum/EIPs/pull/1848) Fork Names Standard	| Not yet discussed in gitter AMA or dev call 	| None planned	|  	|
| **Storage gas cost** | [1884](https://eips.ethereum.org/EIPS/eip-1884) Repricing for trie-size-dependent opcodes 	| SLOAD is affected by both 1884 and 2035	| None planned	| Martin Holst Swende (1884) and Alexey Akhunov (2035) to coordinate preferred SLOAD modification	|
| **Account versioning** | ~~[1891 PR](https://github.com/ethereum/EIPs/pull/1891) Contract-based Account Versioning~~	| Given 1702 progressing, 1891 is redundant. | None planned	| -	|
| **Elliptic curve** | [1930](https://eips.ethereum.org/EIPS/eip-1930) CALLs with strict gas semantic. Revert if not enough gas available	| Not yet discussed in gitter AMA or dev call 	| None planned	| |
| **Chain metadata** | ~~[1959](https://eips.ethereum.org/EIPS/eip-1959) New Opcode to check if a chainID is part of the history of chainIDs~~	| Not needed, given superceded by 1965 which is progressing. 	| None planned	| -	|
| **Elliptic curve** | [1962](https://eips.ethereum.org/EIPS/eip-1962) EC arithmetic and pairings with runtime definitions	| Not yet discussed on dev call | 21 June Dev Call | Alexander Vlasov (@shamatar) will attend [21 June dev call](https://github.com/ethereum/pm/issues/102) to present EIP. See ****Elliptic curve** cluster** for related EIPs |
| **Chain metadata** | [1965](https://eips.ethereum.org/EIPS/eip-1965) Method to check if a chainID is valid at a specific block Number	| No issues | None planned	| -	|
| - | ~~[1985](https://eips.ethereum.org/EIPS/eip-1985) Sane limits for certain EVM parameters~~	| Not yet discussed in gitter AMA or dev call. [Looks like](https://ethereum-magicians.org/t/eip-1985-sane-limits-for-certain-evm-parameters/3224/6) this doesn't need a hard fork 	| None planned	|  Non-istanbul client implementations	|
| **Chain metadata** | [2014](https://eips.ethereum.org/EIPS/eip-2014) Extended State Oracle	| There are concerns that ChainID should be removed from the EIP 	| None planned	|  	Parties interested in moving the EIP ahead should discuss in the [forum](https://ethereum-magicians.org/t/eip-2014-extended-state-oracle/3301/5) |
| **Elliptic curve** | [2024 PR](https://github.com/ethereum/EIPs/pull/2024) Proposal for supporting Blake2b and Blake2s	| No issues. Existing Golang implementation for [blake2b](https://github.com/golang/crypto/tree/master/blake2b) and [blake2s](https://github.com/golang/crypto/tree/master/blake2s)| None planned	| Work toward 2b and 2s implementations for istanbul 	|
| - | [2025 PR](https://github.com/ethereum/EIPs/pull/2025) Funding ETH1.X through a Developer Block Reward for 18 Months	| Minimal voices for or against have been heard 	| None planned	| Would you like to see funding for improving core ethereum? Gather support on any forum you see fit and bring your evidence to the [EIP notes](https://github.com/MadeofTin/EIPs/issues/9)! |
| **State rent** | [2026](https://eips.ethereum.org/EIPS/eip-2026) State Rent H - Fixed Prepayment for accounts	| Not yet discussed in gitter AMA or dev call 	| None planned | POC Implementation WIP 	|
| **State rent** | [2027](https://eips.ethereum.org/EIPS/eip-2027) State Rent C - Net contract size accounting	| Not yet discussed in gitter AMA or dev call 	| None planned	| POC Implementation WIP 	|
| - | [2028](https://eips.ethereum.org/EIPS/eip-2028) Calldata gas cost reduction	| No specific cost has been proposed 	| None planned	| Authors to propose a [specific cost](https://ethereum-magicians.org/t/eip-2028-calldata-gas-cost-reduction/3280/5)	|
| **State rent** | [2029](https://eips.ethereum.org/EIPS/eip-2029) State Rent A - State counters contract	| Not yet discussed in gitter AMA or dev call 	| None planned	| POC Implementation WIP 	|
| **State rent** | [2031](https://eips.ethereum.org/EIPS/eip-2031) State Rent B - Net transaction counter	| Not yet discussed in gitter AMA or dev call 	| None planned	| POC Implementation WIP 	|
| **Storage gas cost** | [2035](https://eips.ethereum.org/EIPS/eip-2035) Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs	| SLOAD is affected by 1884 and 2035 	| None planned	| Martin Holst Swende (1884) and Alexey Akhunov (2035) to coordinate preferred SLOAD modification	|
| **Storage gas cost** | [2045](https://github.com/ethereum/EIPs/pull/2045) add EIP for fractional gas costs	| None 	| None planned	| -	|
| **Elliptic curve** | [2046](https://eips.ethereum.org/EIPS/eip-2046) Reduced gas cost for static calls made to precompiles	| 2046 conflicts with 1109.   	| Any volunteer to discuss with Jordi (1109) on the next ACD call?	| Alex Beregszaszi (2046), Jordi Baylina (1109) and **elliptic curve** stakeholders need to [discuss](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447) 	|


</div>

Some EIPs are complementary and some are mutually exclusive improvements that deprecate other proprosals. Below is a rough clustering to highlight these relationships. 

Edits are welcome.


### **Proposals that are independent / not clustered below**
EIPs with minimal interactions with other proposals
- [1057 ProgPoW, a Programmatic Proof-of-Work](https://eips.ethereum.org/EIPS/eip-1057) (Kristy-Leigh Minehan)
- [1380 Reduced gas cost for call to self](https://eips.ethereum.org/EIPS/eip-1380) (Alex Beregszaszi, Jacques Wagener)
- [1559 Fee market change for ETH 1.0 chain](https://eips.ethereum.org/EIPS/eip-1559) (Vitalik Buterin, Eric Conner)
- [1803 Rename opcodes for clarity](https://eips.ethereum.org/EIPS/eip-1803) (Alex Beregszaszi)
- [1848 Fork Names Standard](https://github.com/ethereum/EIPs/pull/1848) (Christoph Jentzsch)
- [1985 Sane limits for certain EVM parameters](https://eips.ethereum.org/EIPS/eip-1985) (Alex Beregszaszi, Paweł Bylica)
- [2025 Funding ETH1.X through a Developer Block Reward for 18 Months](https://github.com/ethereum/EIPs/pull/2025) to improve [present-day ethereum](https://github.com/MadeofTin/EIPs/blob/ETH1.X/EIPS/eip-2025.md) (James Hancock)
- [2028 Calldata gas cost reduction](https://eips.ethereum.org/EIPS/eip-2028) (Alexey Akhunov, Eli Ben Sasson, Tom Brand, Avihu Levy). There's a lot of excitement about how this EIP will enable/enhance [STARK-based L2 engines](https://twitter.com/PhABCD/status/1129084899225481216), [proof verifications, plasma and state channels](https://twitter.com/PhABCD/status/1135550170643542016).


### **Elliptic curve cluster**


#### Key benefits: 
Scaling, privacy, bridges to other chains, DNS certificate validation in ENS, forward compatibility with IPFS.

Curves enabled and possible uses:
- The alt_bn128 curve (cheaper with 1108).
- Edwards curves (Weierstrass form) in general (cheaper with 1829). This covers curves of the naming convention 'Ed-'.
- Ed25519 is specifically enabled by 665.
- [LibSNARK](https://github.com/scipr-lab/libsnark/tree/f7c87b88744ecfd008126d415494d9b34c4c1b20) which uses edwards 'ed-', bn128 or alt_bn128 curves]. Edwards curves are made cheaper with 1829. The alt_bn128 curve is are made cheaper with 1108).
- Aztec (made cheaper with 1108) which uses [alt_bn128](https://github.com/AztecProtocol/AZTEC)
- Private ERC20/721 transactions on ethereum mainnet with Nightfall (public domain code made by EY) (made cheaper with 1108) using [alt_bn128](https://github.com/EYBlockchain/nightfall/issues/14)
- [Matter labs](https://github.com/matter-labs/matter-network) scaling solution uses Alt_bn128
- [Roll up](https://github.com/barryWhiteHat/roll_up) (made cheaper with 1829), a layer 2 scaling solution which uses the baby jubjub library with the [EdDSA curve](https://github.com/barryWhiteHat/baby_jubjub)
- ZK mixer [miximus](https://github.com/barryWhiteHat/miximus) which uses LibSNARK.
- [Zether](https://crypto.stanford.edu/~buenz/papers/zether.pdf) privacy solution, currently using alt_bn128. See section 7.3 of the paper for how 1108 and 1109 EIPs could bring zether transfers down to 1.7 million gas.
- DNSSEC and TLS integration with ENS is enabled by using Ed25519, which is enabled with 665. There is a list of projects [also using this curve](https://ianix.com/pub/ed25519-deployment.html), including OpenSSH, GNUPG/OpenPGP and OpenBSD.
- Verifying BLS12-381 signatures on ethereum Beacon Chain, enabled by 1962.
- Forward compatibility validation of signatures in IPFS, which are upgrading to use Blake2b (covered by 2024).
- Validating ZCash Blake2b signatures, possibly allowing a bridge to wrap ZEC (WZEC) on ethereum (covered by 2024).

Curves in the ecosystem not related to the Istanbul EIPs
- Secp256k1 was mentioned as an enhancement for [Zether](https://crypto.stanford.edu/~buenz/papers/zether.pdf). This [can be achieved](https://github.com/ethereum/EIPs/issues/603#issuecomment-440095368) already by using ECADD and ECMUL and a dedicated precompile is not planned.
- secp384r1 for Estonia e-residency. Unclear if enabled by ECADD/ECMUL precompiles from 1829

#### Relevant EIPs:
- [1829 Precompile for Elliptic Curve Linear Combinations](https://eips.ethereum.org/EIPS/eip-1829) (Remco Bloemen)
- [1962 EC arithmetic and pairings with runtime definitions](https://eips.ethereum.org/EIPS/eip-1962) (Alex Vlasov)
- [1109 PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)](https://eips.ethereum.org/EIPS/eip-1109) (Jordi Baylina)
- [1108 Reduce alt_bn128 precompile gas costs](https://eips.ethereum.org/EIPS/eip-1108) (Antonio Salazar Cardozo, Zachary Williamson)
- [2024 Proposal for supporting Blake2b](https://github.com/ethereum/EIPs/pull/2024) (James Hancock)
- [2046 Reduced gas cost for static calls made to precompiles](https://eips.ethereum.org/EIPS/eip-2046) (Alex Beregszaszi)
- [1930 CALLs with strict gas semantic. Revert if not enough gas available](https://eips.ethereum.org/EIPS/eip-1930) (Ronan Sandford)

#### Key concepts and EIP interactions

**Introduce new curves using elliptic curve arithmetic with either 1962 (preferred) or 1829**

Both 1829 and 1962 allow for new curves to be added later without waiting for specific precomiples to be included in hard forks. 1829 Allows a class of eliptic curves (Edward curves) to be supported through a precompile for linear combinations. 1962 is a precompile that extends and formalises 1829. 1962 features (as compared to 1829) three main differences:
- Operation on arbitrary-length modulus (up to some upper-limit) for a base field and scalar field of the curve
- Pairing operations are introduced
- Different ABI due to variable parameter length

There were [no supporting arguments in a recent discussion](https://gitter.im/ethereum/AllCoreDevs?at=5cf52f58ff3f016baa9a64c7) for 1829, and 1962 is progressing well. 1962 requires either 1109 or 2046 to make calls economically viable (see below).

**How to define a precompile? (address range with 1352 vs client-based lists of known precompiles)**

1352 is still a **maybe** and the decision of "how do we define what a preompile is" is up for discussion. While it creates a nice range for defining what precompiles are, which [may help](https://gitter.im/ethereum/AllCoreDevs?at=5cf543c5702b7e5e7621ed0f) with static analysis, there are some serious [concerns on FEM](https://ethereum-magicians.org/t/eip-1352-restricted-address-range-for-precompiles-system-contracts/1151/26) about safety. It was clarified that 1352 is not required explicitly by either 1109 or 2046, so either of those can be chosen, but they may need to be modified to be clear about how the define a precompile. **Action required**: Decide if precompiles should be defined by range (push forward with 1352) or client based [lists](https://gitter.im/ethereum/AllCoreDevs?at=5cf53cd06f530d3b612d9c96) (shelve 1352).

**Make precompile call costs cheaper, either by modifying an existing opcode (2046) or introducing a new opcode (1109)**

The goal is to make precompiles cheaper. Both EIPs seek to make 1108, 2024 and 1962 cheaper by reducing the cost of calling a precompile. The decision of 1109 vs 2046 is still **undecided**. The [options](https://gitter.im/ethereum/AllCoreDevs?at=5cf53d0bfaac6439343331a3) for calling precompiles are either to create a new opcode (choose 1109) or to modify the semantics of STATICCALL if the destination is a precomile. **Action required**: Decide if we prefer a new opcode or to modify an old opcode.

**DOS attack mitigation**

There was a [discussion](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/8) about DOS attacks from calls that result in disk loading being too cheap. It seems that as long as the opcode being made cheaper only applies to precompiles, then [there is no risk](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/9). 

1930 Adds the ability to make calls with specific amounts of gas, with a revert endpoint, through new variants of STATICCALL, DELEGATECALL and CALL. This [may benefit EIPs](https://gitter.im/ethereum/AllCoreDevs?at=5cf576215de053468b08b9b8) that modify CALL/STATICCALL behaviour. The winner out of 1109 vs 2046 will need to be checked against 1930 to ensure behaviour is as expected.  

**Specific curve optimisations:**

There is a lot of interest in enabling immediate use of specific curves. Alt_bn128 is enabled by 1108 which supplements 1829 by reducing the cost of addition, multiplication and and pairing checks. Blake2b is enabled by 2024 which introduces a specific precompile for Blake2b for immediate use. Both 1108 and 2024 can coexist with 1962 [without issue](https://gitter.im/ethereum/AllCoreDevs?at=5cf4d34a6fc5846bab533deb)

#### Key questions to ask moving forward:
- Do people want to define precompiles as address ranges (as in 1352) or do they prefer client based lists (status quo). If 1352 is preferred, the concerns in the discussion-to forum need addressing.
- Do people want the new PRECOMILEDCALL opcode in 1109 to call precompiles with or is 2046 preferred, which changes the STATTICALL behaviour when the destination is a precompile?
- Are there any concerns about DOS attacks that only make calls to precompiles cheaper? None have been voiced, and any concerns should be raised [here](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/9)


#### Probable path forward
- Prepare for Istanbul: 1108, 2024, 1962, (1109 vs 2046)
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: 1829



### **Storage writing cluster**


#### Key benefits:
- 1283 allows multiple write operation within a single call frame, allowing re-entry locks and multi-sends which are important for synchronus cross-dapp interactions..

#### Relevant EIPs:
- [1283 Net gas metering for SSTORE without dirty maps](https://eips.ethereum.org/EIPS/eip-1283) (Wei Tang). Clients already have implementations. The spec has been reviewed by many people. Previously had a re-entrancy bug [caused by contracts assuming long term stability of gas costs](https://ethereum-magicians.org/t/immutables-invariants-and-upgradability/2440) which is now addressed with either **account versioning** or with 1706. There have been in-depth about choices of different net gas metering options (EIP-1087, EIP-1153, EIP-1283).
- [1706 Disable SSTORE with gasleft lower than call stipend](https://eips.ethereum.org/EIPS/eip-1706) (Alex Forshtat, Yoav Weiss). 1706 is a required for 1832 to be compatible with many existing contracts if no account versioning is implemented.

#### Key concepts:
- Net gas metering is a [desired](https://gitter.im/ethereum/AllCoreDevs?at=5cfa29c1cea8295279090c00) feature. This can be provided with 1283 in a timely fashion without depending on the State Rent EIPs, through the use of account versioning.
- Net gas metering significantly reduces the gas cost for mutex and multi-step token transfers, which are necessary for synchronous cross dapp interactions. Benefits include improving [uniswap](https://gitter.im/ethereum/AllCoreDevs?at=5cfa77c8481ef4167be72d39).
- Even if account versioning goes ahead and 1706 is not explicitly required, it is simple to implement and would avoid future issues with repricing as noted [here](https://gitter.im/ethereum/AllCoreDevs?at=5cfa2cb465392c3b60d43ba6).
- If net gas metering ends up being implemented as part of the State Rent pathway in Istanbul, 1283 would be made redundant, but would [not cause](https://gitter.im/ethereum/AllCoreDevs?at=5cfa29c1cea8295279090c00) any issues as long as is implemented with account versioning. Given 1283 is strongly desired, implementing it even if metering is planned for State Rent seems preferred.

#### Key decisions:
- Are there any opposed to implementing 1706 even if not explicitly required by 1283 (that is, if account versioning goes ahead)? If no, people need to review the 1706 [implementation](paritytech/parity-ethereum#10191) (the original fix for 1283).


#### Probable path forward
- Prepare for Istanbul: 1283, 1706
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: None



### **Account versioning cluster**

Link to previous Core Dev gathering presentation on account versioning: https://git.that.world/talks/20190417-account-versioning.git/plain/presentation.pdf

#### Key benefits: 
Versioning enables eWASM to coexist with EVM in one block and makes future EVM upgrades safer. Included in the account versioning group is the EVM upgrade (615) that enables static jumps, which enable strong formal analysis of contracts

#### Relation to Previous Hardfork postmortem
For Istanbul, we have some EIPs that propose to decrease operation costs. As part of the last hard fork postmortem, one of the main reason the re-entry bug happened is because EIP-1283 was the first to-be-on-mainnet EIP that includes gas cost decrement. Later in the discussion, it's generally agreed that if we ever want to do another gas/operation cost decrement, we'd either need extra assessment, or it needs to be combined with account versioning.

As a result, account versioning EIPs affect a larger portion of Istanbul EIPs than what's listed above.

#### Relevant EIPs:
- [1702 Generalized Account Versioning Scheme](https://eips.ethereum.org/EIPS/eip-1702) (Wei Tang)
- [1707 Use Version Byte Prefix for Contract Account Versioning](https://github.com/ethereum/EIPs/pull/1707) (Wei Tang)
- [1712 Disallow Deployment of Unused Opcodes](https://github.com/ethereum/EIPs/pull/1712) (Wei Tang)
- [1891 Contract-based Account Versioning](https://github.com/ethereum/EIPs/pull/1891) (Wei Tang)
- [615 Subroutines and Static Jumps for the EVM](https://eips.ethereum.org/EIPS/eip-615) (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner)
- [663 Unlimited SWAP and DUP instructions](https://eips.ethereum.org/EIPS/eip-663) (Alex Beregszaszi)

#### Key concepts:
Versioning:
- EVM versions allow older (dynamic jumping contracts) and newer (static jumping contracts) to co-exist.
- EVM versions allow eWASM contracts and EVM contracts to co-exist within one block.
- EVM versions allow EVM upgrades to guarantee that the behaviour of [older contracts is better preserved](https://ethereum-magicians.org/t/immutables-invariants-and-upgradability/2440/30)
- See presentation on versioning [here](https://git.that.world/talks/20190417-account-versioning.git/plain/presentation.pdf)

EVM upgrade to enable static jumps:
- Dynamic jumps are [hugely problematic](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/25) for contract analysis (control-flow, data-flow, static and formal) and are going to eventually be deprecated. This will be achieved by first by introducing static jumps and subroutines then by later discouraging dynamic jumps entirely. Static jumps significantly lower the bar for static analysis during [formal verification of smart contracts](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/58)
- Static jumps are introduced by moving the frame pointer/returner to new stack and by treating subroutines arguments as local variables
- A dynamic jump is theoretically slower because takes a binary search of a table of every JUMPDEST in the program O(log n) vs O(1) for static jumps, however no testing has confirmed a realised speed gain.
- Static jumps and subroutines are introduced in a single EIP (rather than multiple EIPs) to harness the momentum and get the change implemented, rather than first implementing subroutines (composed of dynamic jumps) then static jumps in a separate fork. The individual components (if split into mulptiple EIPs) [are mostly useless in isolation](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/56)
- 615 [has an implementation](https://gitter.im/ethereum/AllCoreDevs?at=5cf1660d6bec22299e6fa254) for ethereum client devs to model their implementations on.
- While there are ten new opcodes introduced by 615, each opcode is [mapped](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/44) to a similar functional element in eWASM.

#### EIP interactions
- 615 requires one of the account versioning proposals to go ahead (1702, 1707/1217 or 1891)
- 663 is [made redundant](https://github.com/ethereum/EIPs/pull/663#issuecomment-318838695) by 615 through the use of [PUTLOCAL and GETLOCAL](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/33). It would also [break safety guarantees](https://gitter.im/ethereum/AllCoreDevs?at=5cf7f34bf31ba302588e445a) if co-implemented with 615.


Three account versioning proposals, only one must be selected
- **1702 (preferred)**. The EIP has two variants, with the second variant being preferred (In the EIP see under Specification -> Contract Deployment -> [Alternative Design](https://eips.ethereum.org/EIPS/eip-1702))
- 1707 + 1712 (likely not for istanbul). Version as RLP item based on code header prefix. Possibly backward incompatible.
- 1891 (likely not for Istanbul). Store version in a dedicated contract, and [use new opcodes VCREATE/VCREATE2 to get version](https://github.com/ethereum/EIPs/pull/1891/files). Compared to other two solutions will have worse performance (extra to call to state trie), but is less complex and benefits by: 1) Allowing account state format to stay the same, 2) allowing precompile invocation to stay the same and 3) by preventing forging of version bytes.

**1702 flavours: 1 without-code-prefix (not preferred) and 2 with-code-prefix (preferred)**
- Design 1: A contract can only deploy subcontract with the same version.Requires either only allowing deploying "newest" version, or achange in RLP structure in contract creation transactions.
- Design 1 variant makes contract deployment transaction deploys a contract family, and only allow newest account version to be deployed at root. Once we deploy newer versions (like eWASM), older versions (like EVM) should not be able to be deployed again. This is just architecturally simple. EIP-1702 author Wei Tang slightly prefers this, but is not compatible with 615.
- Design 2: All version that is not zero requires a code prefix (such as\0asm). It can be variable length, but must be unique.
- Design 2 variant allows all versions to be deployed, but it requires contract header prefix for all subsequent account versions. This variant [is preferred](https://gitter.im/ethereum/AllCoreDevs?at=5cf6733c82e5c67322287ece) by the 615 team. This option has rough [consensus](https://gitter.im/ethereum/AllCoreDevs?at=5cf68498f3a60a79a451a78b), and is [preferred](https://gitter.im/ethereum/AllCoreDevs?at=5cf68f41b76eac527aa0c4cb) by the Wei Tang (1702 author) because contracts that use CREATE2 would not have to inherit the version of the factory contract.

#### Key questions to ask moving forward:
- Is there any strong opposition to 1702-design-2 (account versioning with code prefix)? If no, then 1707, 1712 and 1891 can be shelved.
- Are more hands needed on deck for 615? Feist Josselin from Trail of Bits is excited about the possibilities this enables for formal verification and was [interested in helping](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/85) to get it into Istanbul. Maybe some help could be offered to the solidity team and testing team for the next-steps as mentioned by Greg [here](https://gitter.im/ethereum/AllCoreDevs?at=5cf1660d6bec22299e6fa254).

#### Probable path forward
- Prepare for Istanbul: 615, 1702 ("design 2 / alternate version / account version with-code-prefix").
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: 663, 1891, 1707, 1712

### **Storage gas cost cluster**

#### Key benefits:
Some opcodes are mispriced, and by repricing them more transations could fit into blocks.
A separate new counter that counts gas with more granularity prepares clients for how eWASM contracts meter gas.

#### Relevant EIPs:
- [1884 Repricing for trie-size-dependent opcodes](https://eips.ethereum.org/EIPS/eip-1884) (Martin Holst Swende)
- [2035 Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs](https://eips.ethereum.org/EIPS/eip-2035) (Alexey Akhunov)
- [2045 add EIP for fractional gas costs](https://github.com/ethereum/EIPs/pull/2045) (Casey Detrio)

#### Key concepts
Current gas costs do not reflect the true CPU cost of operations. In particular, SLOAD and BALANCE are overpriced. 1884 Increases SLOAD and BALANCE gas costs, to properly reflect real relative CPU-time cost. A new opcode SELFBALANCE is also introduced.

2045 Introduces a new gas counter `particles` to be used in eWASM and changes gas costs of storage.

#### EIP interactions
Other EIPs that affect storage gas costs might be:
- 2035 Part of the **state rent** roadmap, also increases SLOAD in order to allow better block proof transmission. 

#### Key questions
- Are there any concerns with the planned path below?

#### Probable path forward
- Prepare for Istanbul: 1884, 2045, probably 2035 (see **state rent** cluster)
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: None

### **Chain metadata cluster**

#### Relevant EIPs:
- [1965 Method to check if a chainID is valid at a specific block number](https://eips.ethereum.org/EIPS/eip-1965) (Ronan Sandford)
- [1959 New Opcode to check if a chainID is part of the history of chainIDs](https://eips.ethereum.org/EIPS/eip-1959) (Ronan Sandford)
- [1344 ChainID opcode](https://eips.ethereum.org/EIPS/eip-1344) (Richard Meissner, Bryant Eisenbach)
- [2014 Extended State Oracle](https://eips.ethereum.org/EIPS/eip-2014) (Alex Beregszaszi)

#### Key concepts:
1965 Adds a precompile to get the ChainID at a specific block number. This supercedes 1959, which introduces ChainID as a new opcode, but likely has reduced fork freedom.

1344 introduces ChainID via a smart contract, which could theoretically co-exist with 1965, but provides same function and likely has a replay vulnerability (as noted in the 1965 EIP rationale). There may be some utility in using both 1344 and 1965 at the time of a hard fork to allow transactions to traverse the fork more cleanly, as discussed in the [forum](https://ethereum-magicians.org/t/eip-1344-add-chain-id-opcode/1131/92)

2014 Introduces an extensible contract system to bring more data to smart contracts, including block hashes and chain identifiers, using the contract ABI encoding. Might be used with 1965 or 1959 to check the validity of the chain identifier for a block. There are concerns in the EIP discussion [thred](https://ethereum-magicians.org/t/eip-2014-extended-state-oracle/3301/5) that including a method for chain ID in this EIP is complex and not wise.

#### Key Questions
- Should 2014 be modified to exclude the method for ChainID?
- Is there anyone who thinks that 1344 is not needed, given that 1965 is going ahead? 

#### Probable path forward
- Prepare for Istanbul: 1344, 1965, 2014
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: 1959

### **State rent cluster**
#### Key benefits
Maintain present-day ethereum by making optimisations that keep state size small

#### Key concepts:

State rent proposal is planned as a [gradual upgrade](https://medium.com/@akhounov/state-rent-changes-for-the-next-ethereum-hard-fork-f68a826558c5) over multiple hard forks. Proposals by Alexey Akhunov.

Planned prototyping and implementation, in order of decreasing priority:
- Change C: Net contract size accounting, [2027](https://eips.ethereum.org/EIPS/eip-2027). Also useful for snapshot sync and better pricing for SLOADs
- Changes A & B: State counters contract [2029](https://eips.ethereum.org/EIPS/eip-2029) & net transaction counter [2031](https://eips.ethereum.org/EIPS/eip-2031)
- Change H: Fixed rent prepayments [2026](https://eips.ethereum.org/EIPS/eip-2026)
- Stateless clients: Repricing SLOAD and SSTORE to pay for block proofs [2035](https://eips.ethereum.org/EIPS/eip-2035) (See also **storage gas cost** cluster above)

#### Key Questions:
- Is net gas metering best paired with the state rent proposal here or directly via 1283 as discussed in the **storage writing cluster**?

#### Probable path forward
- Prepare for Istanbul: (In decreasing priority) 2027, 2029, 2031, 2026, 2035
- Prepare for April 2020 Hard Fork: Those that aren't ready for Istanbul
- Shelve indefinitely: None
# Updates
_Newest at the top, likely EthCatHerders repo / Github project will be source of updates going forward_

* Reviewed on [Core Devs call 60](https://github.com/ethereum/pm/issues/95), including call for PRs to 1679
* Discussed on [Core Devs call 57](https://github.com/ethereum/pm/issues/83), no one disagreed with current timelines
* There is a WIP [Client Tracker](/roadmap/istanbul/tracker)
* EthCatHerders organizing, see [PM repo](https://github.com/ethereum-cat-herders/PM/tree/master/Hard%20Fork%20Planning%20and%20Coordination), Joseph DeLong point of contact for Istanbul 
* Afri proposed the [schedule on the Jan 4th All Core Devs call](https://github.com/ethereum/pm/issues/66#issuecomment-450840440) where it was provisionally accepted




