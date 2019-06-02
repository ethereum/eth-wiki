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

### EIP AMAs on All Core Devs Gitter

To reduce the load on discussing each EIP in the dev calls, some EIPs will be allocated a day in which concerns, comments suggestions and plans may be discussed in the [AllCoreDevs gitter](https://gitter.im/ethereum/AllCoreDevs). The date of any such AMAs can be recorded in the table below for planning and for archival reference.

**Elliptic curve cluster**: Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs): 

**Account versioning cluster**: Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs): 

**Chain metadata cluster**: Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs): 

**Storage writing cluster** and any of the more **independent EIPs** that people want to discuss: Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)

**Storage gas cost cluster** Fri 7th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs): 

**Live All Core Devs Call**: 
- For EIPs people feel are maturing enough to be considered for acceptance into Istanbul should add a comment to [7 June All Core Devs Call Agenda](https://github.com/ethereum/pm/issues/102) with a note about intention (e.g. I intend to briefly present EIP xyz for consideration for acceptance into Istanbul). 
- Call attendees can then read up on the EIP beforehand so that decisions can be made effectively during the call.
- Attending the call to present your EIP goes a long way to getting the change included in Istanbul.

<img src="https://docs.google.com/drawings/d/e/2PACX-1vS7t5kwTrxL3zja2hLIPcNchPtBoXBeSxWNG8-tm5vlGPV4XycY7PMQDWKQGRXd_vwEPLO8dIbPR7EH/pub?w=2762&amp;h=1430">


### Roadblock Spotter

Below is a one-glance table to summarise the current roadblock for each EIP. The table serves to remind what has been most recently discussed in various channels, including All Core Dev Calls. If a roadblock has been addressed, feel free to remove it from the table. If there are concerns about the suitability of an EIP or its fitness for consideration, please add a note here, but take discussions to the the forum listed in the individual EIP. 'Checkpoint issues', such as and EIP not yet having a major client implementation or not having yet submitted test cases are considered 'standard preparations', which are [tracked](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0) for each EIP and are not included below.


<div align="center">

| Cluster | EIP  | Any [non-checkpoint](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0) issue preventing suitability for Istanbul? 	| Gitter AMA or ACD call date 	| Step required 	|
|---	|--- |---	|---	|---	|---	|
| **Account versioning** | [615](https://eips.ethereum.org/EIPS/eip-615) Subroutines and Static Jumps for the EVM	| [In the last dev call Martin Swende](https://youtu.be/lF_XxqxgVuA?t=883) thought that the overhead was greater than benefits of formal analysis and that it was too complex to co-implement with account versioning. [Zachary Williamson noted](https://youtu.be/lF_XxqxgVuA?t=1308) that the performance benefits would be significant. [Feist Josselin is excited about the possibilities this enables for formal verification and is interested in looking into roadblocks to get it into Istanbul](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/85) | Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Check with Feist Josselin at Trail of Bits to see if still interested in assisting. See **account versioning** cluster below for additional notes and questions.  |
| **Account versioning** | [663](https://eips.ethereum.org/EIPS/eip-663) Unlimited SWAP and DUP instructions	| [Alexey noted it solves same stack-access problem as 615](https://youtu.be/lF_XxqxgVuA?t=1934). Three technical options are presented. 	| Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Alexey Akhunov, Alex Beregszaszi (663), 615 authors (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner) need to discuss and resolve. Decide if 615 goes ahead, and if so is 663 still needed?	|
| - | [689](https://eips.ethereum.org/EIPS/eip-689) Address Collision of Contract Address Causes Exceptional Halt	| [Not needed](https://youtu.be/lF_XxqxgVuA?t=283). No hard fork required and is covered by [issue 684](https://github.com/ethereum/EIPs/issues/684) 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)| Non-istanbul client implementations	|
| - | [1057](https://eips.ethereum.org/EIPS/eip-1057) ProgPoW, a Programmatic Proof-of-Work	| Audit may find hardward/software issues. Danno notes that [a small addition is required](https://ethereum-magicians.org/t/eip-progpow-a-programmatic-proof-of-work/272/13) 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Danno Ferrin to implement addition. Work on client implementations as if will go in. If audit happens and issue found, may need to delay to April hard fork. 	|
| **Elliptic curve** | [1108](https://eips.ethereum.org/EIPS/eip-1108) Reduce alt_bn128 precompile gas costs	| Benchmarks [incomplete](https://youtu.be/lF_XxqxgVuA?t=2896) 	| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Zachary Williamson to re-run benchmarks. Mariano Conti [is offering help if needed](https://twitter.com/nanexcool/status/1134583012748869634) 	|
| **Elliptic curve** | [1109](https://eips.ethereum.org/EIPS/eip-1109) PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)	| 2046 conflicts with 1109. 	| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Alex Beregszaszi (2046), Jordi Baylina (1109) and **elliptic curve** stakeholders need to [discuss](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447) |
| **Storage writing** | [1283](https://eips.ethereum.org/EIPS/eip-1283) Net gas metering for SSTORE without dirty maps	| Need to decide if metering goes on EVM or alongside sate rent pathway. As per dev call #61 Possibly needs new EIP which explains differences between [EIP 1087](https://eips.ethereum.org/EIPS/eip-1087) and [EIP 1283](https://eips.ethereum.org/EIPS/eip-1283) 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Decide if metering on EVM or with state rent. Does Wei Tang submit new EIP comparing to 1087? 	|
| **Chain metadata** | [1344](https://eips.ethereum.org/EIPS/eip-1344) ChainID opcode	| [Danno noted that 1965, 1959 and 1344 do the same thing](https://youtu.be/lF_XxqxgVuA?t=3696). 	| Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Danno Ferrin, Ronan Sandford (1965, 1959), 1344 authors (Richard Meissner and Bryant Eisenbach) and **chain metadata** stakeholders to elect preferred method	|
| - | [1352](https://eips.ethereum.org/EIPS/eip-1352) Specify restricted address range for precompiles/system contracts	| No hard fork required, but needed for 2046 	| -	| Non-istanbul client implementations	|
| - | [1380](https://eips.ethereum.org/EIPS/eip-1380) Reduced gas cost for call to self	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| - | [1559](https://eips.ethereum.org/EIPS/eip-1559) Fee market change for ETH 1.0 chain	| Péter Szilágyi: [May effect transaction propagation](https://youtu.be/lF_XxqxgVuA?t=4506) Rick Dudley: EIP may not be completed in time 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Rick Dudley to work toward Istanbul and make patch for network propagation 	|
| **Account versioning** | [1702](https://eips.ethereum.org/EIPS/eip-1702) Generalized Account Versioning Scheme	| Conflict between different methods proposed 1702, 1707/1712 and 1891. 	| Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Wei Tang (1702, 1707, 1712 & 1891) and **account versioning** stakeholders including 615 authors (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner) need to discuss and confirm that 1702 is the preferred method	|
| **Storage writing** | [1706](https**://eips.ethereum.org/EIPS/eip-1706) Disable SSTORE with gasleft lower than call stipend	| Depends on whether 1283 goes ahead. Not needed if account versioning goes ahead.	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Make decision about 1283 and versioning (likely 1702)  	|
| **Account versioning** | [1707 PR](https://github.com/ethereum/EIPs/pull/1707) Use Version Byte Prefix for Contract Account Versioning | Conflict between different methods proposed 1702, 1707/1712 and 1891. 	| Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Wei Tang (1702, 1707, 1712 & 1891) and **account versioning** stakeholders including 615 authors (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner) need to discuss and elect preferred method	|
| **Account versioning** | [1712 PR](https://github.com/ethereum/EIPs/pull/1712) Disallow Deployment of Unused Opcodes	| Conflict between different methods proposed 1702, 1707/1712 and 1891. 	| Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Wei Tang (1702, 1707, 1712 & 1891) and **account versioning** stakeholders including 615 authors (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner) need to confirm that 1702 is the preferred method	|
| - | [1803](https://eips.ethereum.org/EIPS/eip-1803) Rename opcodes for clarity	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| **Elliptic curve** | [1829](https://eips.ethereum.org/EIPS/eip-1829) Precompile for Elliptic Curve Linear Combinations	| Not yet discussed in gitter AMA or dev call 	| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| |
| - | [1848 PR](https://github.com/ethereum/EIPs/pull/1848) Fork Names Standard	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| **Storage gas cost** | [1884](https://eips.ethereum.org/EIPS/eip-1884) Repricing for trie-size-dependent opcodes 	| SLOAD is affected by 1884, 2035 and possibly 2045 	| Fri 7th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Martin Holst Swende (1884), Alexey Akhunov (2035) and Casey Detrio (2045) to coordinate preferred SLOAD modification	|
| **Account versioning** | [1891 PR](https://github.com/ethereum/EIPs/pull/1891) Contract-based Account Versioning	| Conflict between different methods proposed 1702, 1707/1712 and 1891. 	| Tues 4th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Wei Tang (1702, 1707, 1712 & 1891) and **account versioning** stakeholders including 615 authors (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner) need to confirm that 1702 is the preferred method	|
| **Elliptic curve** | [1930](https://eips.ethereum.org/EIPS/eip-1930) CALLs with strict gas semantic. Revert if not enough gas available	| Not yet discussed in gitter AMA or dev call 	| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| |
| **Chain metadata** | [1959](https://eips.ethereum.org/EIPS/eip-1959) New Opcode to check if a chainID is part of the history of chainIDs	| [Danno noted that 1965, 1959 and 1344 do the same thing](https://youtu.be/lF_XxqxgVuA?t=3696). 	| Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Danno Ferrin, Ronan Sandford (1965, 1959), 1344 authors (Richard Meissner and Bryant Eisenbach) and **chain metadata** stakeholders to elect preferred method	|
| **Elliptic curve** | [1962](https://eips.ethereum.org/EIPS/eip-1962) EC arithmetic and pairings with runtime definitions	| Not yet discussed on dev call | 7 June Dev Call, may also come up beforehand on Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs) | Alexander Vlasov (@shamatar) will attend [7 June dev call](https://github.com/ethereum/pm/issues/102) to present EIP. See ****Elliptic curve** cluster** for related EIPs |
| **Chain metadata** | [1965](https://eips.ethereum.org/EIPS/eip-1965) Method to check if a chainID is valid at a specific block Number	| [Danno noted that 1965, 1959 and 1344 do the same thing](https://youtu.be/lF_XxqxgVuA?t=3696). 	| Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Danno Ferrin, Ronan Sandford (1965, 1959), 1344 authors (Richard Meissner and Bryant Eisenbach) and **chain metadata** stakeholders to elect preferred method	|
| - | [1985](https://eips.ethereum.org/EIPS/eip-1985) Sane limits for certain EVM parameters	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| **Chain metadata** | [2014](https://eips.ethereum.org/EIPS/eip-2014) Extended State Oracle	| Not yet discussed in gitter AMA or dev call 	| Wed 5th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| **Elliptic curve** | [2024 PR](https://github.com/ethereum/EIPs/pull/2024) Proposal for supporting Blake2b and Blake2s	| Casey: [Zachary Williamson's code / EVM1 opcode repricing/optimisation might be a precompile-free alternative](https://youtu.be/lF_XxqxgVuA?t=5054) Existing Golang implementation for [blake2b](https://github.com/golang/crypto/tree/master/blake2b) and [blake2s](https://github.com/golang/crypto/tree/master/blake2s)| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| JP discuss with BM/CD/ZW whether optimisations will happen [soon enough](https://youtu.be/lF_XxqxgVuA?t=5347), especially as the dedicated Blake2b/2s implementation is [trivial](https://youtu.be/lF_XxqxgVuA?t=5477) and will be valuable 	|
| - | [2025 PR](https://github.com/ethereum/EIPs/pull/2025) Funding ETH1.X through a Developer Block Reward for 18 Months	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| |
| **State rent** | [2026](https://eips.ethereum.org/EIPS/eip-2026) State Rent H - Fixed Prepayment for accounts	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| POC Implementation WIP 	|
| **State rent** | [2027](https://eips.ethereum.org/EIPS/eip-2027) State Rent C - Net contract size accounting	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| - | [2028](https://eips.ethereum.org/EIPS/eip-2028) Calldata gas cost reduction	| Not yet discussed in gitter AMA or dev call 	| Thurs 6th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	|  	|
| **State rent** | [2029](https://eips.ethereum.org/EIPS/eip-2029) State Rent A - State counters contract	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| **State rent** | [2031](https://eips.ethereum.org/EIPS/eip-2031) State Rent B - Net transaction counter	| Not yet discussed in gitter AMA or dev call 	| -	| POC Implementation WIP 	|
| **Storage gas cost** | [2035](https://eips.ethereum.org/EIPS/eip-2035) Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs	| SLOAD is affected by 1884, 2035 and possibly 2045 	| Fri 7th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Martin Holst Swende (1884), Alexey Akhunov (2035) and Casey Detrio (2045) to coordinate preferred SLOAD modification	|
| **Storage gas cost** | [2045](https://github.com/ethereum/EIPs/pull/2045) add EIP for fractional gas costs	| SLOAD is affected by 1884, 2035 and possibly 2045 	| Fri 7th June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Martin Holst Swende (1884), Alexey Akhunov (2035) and Casey Detrio (2045) to coordinate preferred SLOAD modification	|
| **Elliptic curve** | [2046](https://eips.ethereum.org/EIPS/eip-2046) Reduced gas cost for static calls made to precompiles	| 2046 conflicts with 1109.   	| Mon 3rd June UTC [on Gitter](https://gitter.im/ethereum/AllCoreDevs)	| Alex Beregszaszi (2046), Jordi Baylina (1109) and **elliptic curve** stakeholders need to [discuss](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447) 	|


</div>

Some EIPs are complementary and some are mutually exclusive improvements that deprecate other proprosals. Below is a rough clustering to highlight these relationships. 

Edits are welcome.


### **Proposals that are independent**
EIPs with minimal interactions with other proposals
- [1057 ProgPoW, a Programmatic Proof-of-Work](https://eips.ethereum.org/EIPS/eip-1057) (Kristy-Leigh Minehan)
- [1380 Reduced gas cost for call to self](https://eips.ethereum.org/EIPS/eip-1380) (Alex Beregszaszi, Jacques Wagener)
- [1559 Fee market change for ETH 1.0 chain](https://eips.ethereum.org/EIPS/eip-1559) (Vitalik Buterin, Eric Conner)
- [1803 Rename opcodes for clarity](https://eips.ethereum.org/EIPS/eip-1803) (Alex Beregszaszi)
- [1848 Fork Names Standard](https://github.com/ethereum/EIPs/pull/1848) (Christoph Jentzsch)
- [1985 Sane limits for certain EVM parameters](https://eips.ethereum.org/EIPS/eip-1985) (Alex Beregszaszi, Paweł Bylica)
- [2025 Funding ETH1.X through a Developer Block Reward for 18 Months](https://github.com/ethereum/EIPs/pull/2025) to improve [present-day ethereum](https://github.com/MadeofTin/EIPs/blob/ETH1.X/EIPS/eip-2025.md) (James Hancock)
- [2028 Calldata gas cost reduction](https://eips.ethereum.org/EIPS/eip-2028) (Alexey Akhunov, Eli Ben Sasson, Tom Brand, Avihu Levy)


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

**1829 vs 1962:**

Both 1829 and 1962 allow for new curves to be added later without waiting for specific precomiples to be included in hard forks. 

1829 Allows a class of eliptic curves (Edward curves) to be supported through a precompile for linear combinations. 1962 is a precompile that extends and formalises 1829.  

1962 features (as compared to 1829) three main differences:
- Operation on arbitrary-length modulus (up to some upper-limit) for a base field and scalar field of the curve
- Pairing operations are introduced
- Different ABI due to variable parameter length

1962 requires either 1109 or 2046 to make calls economically viable (see below).

**2046 vs 1109:**

Both EIPs seek to make 1108, 2024 and 1962 cheaper by reducing the cost of calling a precompile. 

Because 1962 uses STATICCALL, which is expensive, the cost must be lowered to enable practicle use of curves. It seems that there are two mechanisms to achieve this:
- 1109 makes costs reasonable by introducing a dedicated opcode PRECOMPILEDCALL with a low gas cost so that precompiles can be called efficiently.
- 2046 reduces the cost of calling STATICCALL, but only for precompiles at specific addresses (specified by EIP 1352, which likely does not require a hard fork)

There was a [discussion](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/8) about DOS attacks from calls that result in disk loading being too cheap. It seems that as long as the opcode being made cheaper only applies to precompiles, then [there is no risk](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/9) 

1930 Adds the ability to make calls with specific amounts of gas, with a revert endpoint, through new variants of STATICCALL, DELEGATECALL and CALL. This may affect 2046 which also affects CALL/STATICCALL.

**Specific curve optimisations:**

There is a lot of interest in enabling immediate use of specific curves.

Alt_bn128 is enabled by 1108 which supplements 1829 by reducing the cost of addition, multiplication and and pairing checks.

Blake2b is enabled by 2024 which introduces a specific precompile for Blake2b for immediate use.

#### Key questions to ask moving forward:
- Is it true that 1962 is preferred over 1829, and that 1829 is therefore not needed?
- Is 2046/1352 or 1109 preferred as the mechanism to lower calls to precompiles?
- Is it true that DOS attacks are minimised when the opcode being made cheaper only affects calls to precompiles?
- Is it true that 1352 does not required a hard fork?
- How does 1930 affect the other EIPs, particuarly 2046, given introduces new variants of STATICCALL.
- Is it true that the specific curve optimisations 1108 and 2024 can coexist with the generic elliptic curve building block precompiles (1962).

#### Key actions:
- Decide if 1962 or 1829 are preferred
- Decide if 2046 (modify STATICCALL for precomiles) or 1109 (new PRECOMPILED call) preferred.

#### Probable path forward
- Prepare for Istanbul: 1108, 2024, 1962, (either 2046 or 1109)
- Prepare for April 2020 Hard Fork:
- Shelve indefinitely: 1829

### **Storage writing cluster**

#### Key benefits:
- 1283 allows multiple write operation within a single call frame, allowing re-entry locks and multi-sends.

#### Relevant EIPs:
- [1283 Net gas metering for SSTORE without dirty maps](https://eips.ethereum.org/EIPS/eip-1283) (Wei Tang). Clients already have implementations. The spec has been reviewed by many people. Previously had a re-entrancy bug [caused by contracts assuming long term stability of gas costs](https://ethereum-magicians.org/t/immutables-invariants-and-upgradability/2440) which is now addressed with either **account versioning** or with 1706. There have been in-depth about choices of different net gas metering options (EIP-1087, EIP-1153, EIP-1283).
- [1706 Disable SSTORE with gasleft lower than call stipend](https://eips.ethereum.org/EIPS/eip-1706) (Alex Forshtat, Yoav Weiss). 
1706 is a required for 1832 to be compatible with many existing contracts if no account versioning is implemented.

#### Key decisions:
- Whether to implement net gas metering directly on EVM or implement it once Alexey's state rend has been implemented
- Are account versioning EIPs (likely 1702) happening, (most likely yes) see **account versioning** cluster?
- In AllCoreDevs #61, there was a request for a 1283 to be replaced by new EIP which explains differences between [EIP 1087](https://eips.ethereum.org/EIPS/eip-1087) and [EIP 1283](https://eips.ethereum.org/EIPS/eip-1283). Is this still required?

#### Key actions:
- If gas metering on EVM (1283) desired, and account versioning happens then 1706 is not required
- If gas metering on EVM (1283) desired and no account versioning happening in Istanbul, have people review the 1706 [implementation](paritytech/parity-ethereum#10191) (the original fix for 1283).
- If gas metering to happen once Alexey's state rent goes ahead, plan for metering to happen in synchony with rate rent roadmap in an appropriate fork. (Neither 1283 nor 1087 go into Istanbul).


#### Probable path forward
- Prepare for Istanbul: 1283 (if metering happening directly on EVM)
- Prepare for April 2020 Hard Fork:
- Shelve indefinitely: 1706 (if account versioning goes ahead)

### **Account versioning cluster**


#### Key benefits: 
Versioning enables eWASM to coexist with EVM in one block and makes future EVM upgrades safer.  Static jumps enable strong formal analysis of contracts

#### Relevant EIPs:
- [1702 Generalized Account Versioning Scheme](https://eips.ethereum.org/EIPS/eip-1702) (Wei Tang)
- [1707 Use Version Byte Prefix for Contract Account Versioning](https://github.com/ethereum/EIPs/pull/1707) (Wei Tang)
- [1712 Disallow Deployment of Unused Opcodes](https://github.com/ethereum/EIPs/pull/1712) (Wei Tang)
- [1891 Contract-based Account Versioning](https://github.com/ethereum/EIPs/pull/1891) (Wei Tang)
- [615 Subroutines and Static Jumps for the EVM](https://eips.ethereum.org/EIPS/eip-615) (Greg Colvin, Brooklyn Zelenka, Paweł Bylica, Christian Reitwiessner)
- [663 Unlimited SWAP and DUP instructions](https://eips.ethereum.org/EIPS/eip-663) (Alex Beregszaszi)

#### Key concepts:
- Dynamic jumps are [hugely problematic](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/25) for contract analysis (control-flow, data-flow, static and formal) and are going to eventually be deprecated. This will be achieved by first by introducing static jumps and subroutines then by later discouraging dynamic jumps entirely. Static jumps [significantly lower the bar for static analysis during formal verication of smart contracts](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/58)
- Static jumps are introduced by moving the frame pointer/returner to new stack and by treating subroutines arguments as local variables
- EVM versions allow older (dynamic jumping contracts) and newer (static jumping contracts) to co-exist.
- EVM versions allow eWASM contracts and EVM contracts to co-exist within one block.
- EVM versions allow EVM upgrades to [guarantee that the behaviour of older contracts is better preserved](https://ethereum-magicians.org/t/immutables-invariants-and-upgradability/2440/30)
- A dynamic jump is theoretically slower because takes a binary search of a table of every JUMPDEST in the program O(log n) vs O(1) for static jumps, however no testing has confirmed a realised speed gain.
- Static jumps and subroutines are introduced in a single EIP (rather than multiple EIPs) to harness the momentum and get the change implemented, rather than first implementing subroutines (composed of dynamic jumps) then static jumps in a separate fork. The individual components (if split into mulptiple EIPs) [are mostly useless in isolation](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/56)

#### EIP interactions
- 615 requires one of the account versioning proposals to go ahead (1702, 1707/1217 or 1891)
- 663 increases stack depth, which, if 615 goes ahead [will most likely be unecessary (as per Greg Colvin)](https://github.com/ethereum/EIPs/pull/663#issuecomment-318838695) through the use of [PUTLOCAL and GETLOCAL](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/33).


Three account versioning proposals, only one must be selected
- **1702 (preferred)**. [1702 - See under Specification -> Contract Deployment -> Alternative Design](https://eips.ethereum.org/EIPS/eip-1702)
- 1707 + 1712. Version as RLP item based on code header prefix. Possibly backward incompatible.
- 1891. Store version in a dedicated contract, and [use new opcodes VCREATE/VCREATE2 to get version](https://github.com/ethereum/EIPs/pull/1891/files). Compared to other two solutions will have worse performance (extra to call to state trie), but is less complex and benefits by: 1) Allowing account state format to stay the same, 2) allowing precompile invocation to stay the same and 3) by preventing forging of version bytes.


#### Key questions to ask moving forward:
- Is it true that 663 would provide no additional benefit if 615 goes ahead and can be shelved?
- Are there any concerns around the current consensus to go with 1702 over both 1707+1712 and 1891?
- Precompile invocation is a topic modified by EIPs in the **Elliptic Curve cluster**. Is it true that 1702 will affect the precompile-based EIPs in the **Elliptic curve cluster** which will need some attention?
- 615 [has an implementation](https://gitter.im/ethereum/AllCoreDevs?at=5cf1660d6bec22299e6fa254) for ethereum client devs to model their implementations on. Can we signal to the client teams that yes 615 will go ahead, so that they can work on their implementations?
- What specifically is required of the [solidity team and testing team](https://gitter.im/ethereum/AllCoreDevs?at=5cf1660d6bec22299e6fa254) as a next step for 615?
- Is there are need to prove with testing that static jumps from 615 are faster that dynamic jumps, given there are [significant benefits in contract security analysis (as per Neville Grech)](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/58) which arguably are the main benefit to be had?
- Are there serious technical concerns that require 615 to be split into separate EIPs (First subroutines then static jumps)? 
- While 615 introduces ten new opcodes, which [Bryant Eisenbach](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/39) and [Nick Johnson](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/31) though was a large number. The [opcodes are mapped to similar functional elements in eWASM](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/44) which will help with the EVM->eWASM transition. Are Bryan and Nick happy with this?

#### Probable path forward
- Prepare for Istanbul: 615 and [1702 - See under Specification -> Contract Deployment -> Alternative Design](https://eips.ethereum.org/EIPS/eip-1702))
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: 663, two of the account versioning proposals (most likely 1891 and 1707+1712)

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
- Should the SLOAD parameter used in 1884 and 2035 be compared and a single parameter selected for both?
- Does 2045 affect either 1884 or 2035?

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
1965 Adds a precompile to get the ChainID at a specific block number. This likely supercedes both proposals:
- 1959 Which introduces ChainID as a new opcode, but likely has reduced fork freedom.
- 1344 Which introduces ChainID via a smart contract, which likely has a replay vulnerability.

2014 Introduces an extensible contract system to bring more data to smart contracts, including block hashes and chain identifiers, using the contract ABI encoding. Might be used with 1965 or 1959 to check the validity of the chain identifier for a block.

#### Key Questions
- Is it true that 1965 supercedes 1959 and 1344?

#### Probable path forward
- Prepare for Istanbul: 1965, 2014
- Prepare for April 2020 Hard Fork: None
- Shelve indefinitely: 1959, 1344

### **State rent cluster**
#### Key benefits
Maintainpresent-day ethereum by making optimisations that keep state size small

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




