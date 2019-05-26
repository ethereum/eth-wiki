<!-- TITLE: Istanbul -->
<!-- SUBTITLE: October 2019 Planned Ethereum Network Upgrade -->

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

**Roadblock Unblocker**

Below is a one-glance table to summarise the current roadblock for each EIP. The table serves to remind what has been most recently discussed various channels, including dev calls. If a roadblock has been addressed, feel free to remove it from the table. If there are concerns about the suitability of an EIP or its fitness for consideration, please add a note here, but take discussions to the the forum listed in the individual EIP.

**EIP AMAs on All Core Devs Gitter**: To reduce the load on discussing each EIP in the dev calls, some EIPs will be allocated a day in which concerns, comments suggestions and plans may be discussed in the [AllCoreDevs gitter](https://gitter.im/ethereum/AllCoreDevs). The date of any such AMAs can be recorded here for planning and for archival reference.

<div align="center">

| EIP 	| Any [non-checkpoint](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0) issue preventing suitability for Istanbul? 	| Gitter AMA date	| Step required 	|
|---	|---	|---	|---	|---	|
| [615](https://eips.ethereum.org/EIPS/eip-615) Subroutines and Static Jumps for the EVM	| [MS: 1) Overhead > benefits of formal analysis and ease of mapping in WASM and 2) Complex to co-implement EVM versioning](https://youtu.be/lF_XxqxgVuA?t=883) [ZW: performance benefits significant](https://youtu.be/lF_XxqxgVuA?t=1308)| -	|Benchmark data for benefits, decide if should be in next fork after [versioning](https://eips.ethereum.org/EIPS/eip-1702) has been implemented 	|
| [663](https://eips.ethereum.org/EIPS/eip-663) Unlimited SWAP and DUP instructions	| [AB: solves same stack-access problem as EIP615](https://youtu.be/lF_XxqxgVuA?t=1934) 	| -	| AB discuss with EIP615 authors if option A/B/C could be a precursor to EIP615 	|
| [689](https://eips.ethereum.org/EIPS/eip-689) Address Collision of Contract Address Causes Exceptional Halt	| [Not needed](https://youtu.be/lF_XxqxgVuA?t=283). No hard fork required and is covered by [issue 684](https://github.com/ethereum/EIPs/issues/684) 	| -	| Non-istanbul 	|
| [1057](https://eips.ethereum.org/EIPS/eip-1057) ProgPoW, a Programmatic Proof-of-Work	| Audit may find hardward/software issues. DF: [A small addition is required](https://ethereum-magicians.org/t/eip-progpow-a-programmatic-proof-of-work/272/13) 	| -	| DF to implement addition. Work on client implementations as if will go in. If audit happens and issue found, may need to delay to April HF. 	|
| [1108](https://eips.ethereum.org/EIPS/eip-1108) Reduce alt_bn128 precompile gas costs	| Benchmarks [incomplete](https://youtu.be/lF_XxqxgVuA?t=2896) 	| -	| ZW to re-run benchmarks 	|
| [1109](https://eips.ethereum.org/EIPS/eip-1109) PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)	| AB: [Solves same issue as EIP 2046](https://youtu.be/lF_XxqxgVuA?t=3163) 	| -	| Decide if refining OPCODE (1109) or new opcode (2046) is preferred|
| [1283](https://eips.ethereum.org/EIPS/eip-1283) Net gas metering for SSTORE without dirty maps	| Needs new EIP which explains differences between [EIP 1087](https://eips.ethereum.org/EIPS/eip-1087) and [EIP 1283](https://eips.ethereum.org/EIPS/eip-1283) 	| -	| WT to submit new EIP 	|
| [1344](https://eips.ethereum.org/EIPS/eip-1344) ChainID opcode	| [Opcode vulnerable to replay attack](https://eips.ethereum.org/EIPS/eip-1965) 	| -	| See 1965 	|
| [1352](https://eips.ethereum.org/EIPS/eip-1352) Specify restricted address range for precompiles/system contracts	| No HF required 	| -	| Non-istanbul 	|
| [1380](https://eips.ethereum.org/EIPS/eip-1380) Reduced gas cost for call to self	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1559](https://eips.ethereum.org/EIPS/eip-1559) Fee market change for ETH 1.0 chain	| PS: [May effect transaction propagation](https://youtu.be/lF_XxqxgVuA?t=4506) RN: May not be completed in time 	| -	| RN to work toward Istanbul and make patch for network propagation 	|
| [1702](https://eips.ethereum.org/EIPS/eip-1702) Generalized Account Versioning Scheme	| No issues 	| -	| Continue preparations 	|
| [1706](https://eips.ethereum.org/EIPS/eip-1706) Disable SSTORE with gasleft lower than call stipend	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102)  	|
| [1707 PR](https://github.com/ethereum/EIPs/pull/1707) Use Version Byte Prefix for Contract Account Versioning	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1712 PR](https://github.com/ethereum/EIPs/pull/1712) Disallow Deployment of Unused Opcodes	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1803](https://eips.ethereum.org/EIPS/eip-1803) Rename opcodes for clarity	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1829](https://eips.ethereum.org/EIPS/eip-1829) Precompile for Elliptic Curve Linear Combinations	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1848 PR](https://github.com/ethereum/EIPs/pull/1848) Fork Names Standard	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1884](https://eips.ethereum.org/EIPS/eip-1884) Repricing for trie-size-dependent opcodes 	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1891 PR](https://github.com/ethereum/EIPs/pull/1891) Contract-based Account Versioning	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1930](https://eips.ethereum.org/EIPS/eip-1930) CALLs with strict gas semantic. Revert if not enough gas available	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [1959](https://eips.ethereum.org/EIPS/eip-1959) New Opcode to check if a chainID is part of the history of chainIDs	| [Reduced fork freedom. Likely superceded by 1965](https://eips.ethereum.org/EIPS/eip-1965) 	| -	| See 1959 	|
| [1965](https://eips.ethereum.org/EIPS/eip-1965) Method to check if a chainID is valid at a specific block Number	| DF: [1965, 1959 and 1344 do the same thing](https://youtu.be/lF_XxqxgVuA?t=3696). 	| -	| RS/RM/BE to clarify that 1965 supercedes 1959 and 1344 	|
| [1985](https://eips.ethereum.org/EIPS/eip-1985) Sane limits for certain EVM parameters	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [2014](https://eips.ethereum.org/EIPS/eip-2014) Extended State Oracle	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [2024 PR](https://github.com/ethereum/EIPs/pull/2024) Proposal for supporting Blake2b	| CD: [ZW / EVM1 opcode repricing/optimisation might be a precompile-free alternative](https://youtu.be/lF_XxqxgVuA?t=5054) 	| -	| JP discuss with BM/CD/ZW whether optimisations will happen [soon enough](https://youtu.be/lF_XxqxgVuA?t=5347), especially as implementation is [trivial](https://youtu.be/lF_XxqxgVuA?t=5477) 	|
| [2025 PR](https://github.com/ethereum/EIPs/pull/2025) Funding ETH1.X through a Developer Block Reward for 18 Months	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [2026](https://eips.ethereum.org/EIPS/eip-2026) State Rent H - Fixed Prepayment for accounts	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| [2027](https://eips.ethereum.org/EIPS/eip-2027) State Rent C - Net contract size accounting	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| [2028](https://eips.ethereum.org/EIPS/eip-2028) Calldata gas cost reduction	| Not yet discussed in gitter AMA or dev call 	| -	| Allocate gitter AMA date or EIP champion / a volunteer to present at [7 June dev call](https://github.com/ethereum/pm/issues/102) 	|
| [2029](https://eips.ethereum.org/EIPS/eip-2029) State Rent A - State counters contract	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| [2031](https://eips.ethereum.org/EIPS/eip-2031) State Rent B - Net transaction counter	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| [2035](https://eips.ethereum.org/EIPS/eip-2035) Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| [2045](https://github.com/ethereum/EIPs/pull/2045) add EIP for fractional gas costs	| No issues 	| -	| Continue preparations 	|
| [2046](https://eips.ethereum.org/EIPS/eip-2046) Reduced gas cost for static calls made to precompiles	| See 1109 (solves same issue) 	| C-	| hoose 1109 vs 2046 	|


</div>


# Updates
_Newest at the top, likely EthCatHerders repo / Github project will be source of updates going forward_

* Reviewed on [Core Devs call 60](https://github.com/ethereum/pm/issues/95), including call for PRs to 1679
* Discussed on [Core Devs call 57](https://github.com/ethereum/pm/issues/83), no one disagreed with current timelines
* There is a WIP [Client Tracker](/roadmap/istanbul/tracker)
* EthCatHerders organizing, see [PM repo](https://github.com/ethereum-cat-herders/PM/tree/master/Hard%20Fork%20Planning%20and%20Coordination), Joseph DeLong point of contact for Istanbul 
* Afri proposed the [schedule on the Jan 4th All Core Devs call](https://github.com/ethereum/pm/issues/66#issuecomment-450840440) where it was provisionally accepted


