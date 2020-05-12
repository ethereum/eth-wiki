---
title: Istanbul
description: October 2019 Planned Ethereum Network Upgrade
published: true
date: 2019-12-08T12:08:56.664Z
tags: 
---

The [Etherum 1.x](/eth1) page is a good starting point for an overview of Working Groups and areas of focus.

# Philosophy

Regular small hard forks allow upgrades to be included in more timely and manageable way that large infrequent forks, as described [here](https://ethereum-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28) 

**Istanbul** was approached with a *fork-centric* approach, where EIPs were proposed for the fork, reviewed then accepted. This resulted in many EIPs being proposed, in various states of readiness. This approach limits the amount of review time per EIP. 

 
**Future forks** will ideally follow an *EIP-centric* approach outlined [here](https://notes.ethereum.org/@holiman/S1ELAYY7S?type=view). This approach will allow EIPs to mature independently of forking schedule. When mature, they can be added to the next scheduled fork.

1. Endorsement (by major clients, developers and community stakeholders)
2. Implementation (merged into major clients)
3. Testing
4. Acceptance (Allocate to a specific hard fork)

# TL;DR


Istanbul brings upgrades that will:
- Align the costs of opcodes with their computational costs and improve denial-of-service attack resilience
- Make layer 2 solutions based on SNARKs and STARKs more performant.
- Enable Ethereum and Zcash to interoperate
- Allow contracts to introduce more creative functions.

Specifically:

**[EIP-152](https://github.com/ethereum/EIPs/pull/2129)** Adds the ability to verify the Equihash PoW within an ethereum contract. This will enable a relay and atomic-swap transactions between Zcash.

**[EIP-1108](https://eips.ethereum.org/EIPS/eip-1108)** Makes zk-SNARKs cheaper, allowing for cheaper scaling and privacy applications to be built. See Matter labs, Aztec, Rollup and Zether for examples.

**[EIP-1344](https://eips.ethereum.org/EIPS/eip-1344)** Adds a way for contracts to track the correct chain. To be used by contracts, especially those used by layer 2 (state channels, plasma), to follow the correct layer 1 chain, especially during a hard fork.

**[EIP-1884](https://eips.ethereum.org/EIPS/eip-1884)** Changes the cost of some EVM opcodes to prevent spamming attacks and to balance blocks better. The amount that must be paid for each operation in ethereum usually matches the computation required for that operation. This change increases some costs of some opcodes that are computationally intensive but currently cheap.

**[EIP-2028](https://eips.ethereum.org/EIPS/eip-2028)** Makes zk-SNARKs and zk-STARKs cheaper by reducing the cost of calling data within transactions. This will make layer 2 solutions able to increase throughput.

**[EIP-2200](https://eips.ethereum.org/EIPS/eip-2200)** Changes the calculation of cost of storage in the EVM and will enable contracts to introduce new functions including re-entry locks and same-contract multi-send.

### Road to Istanbul in-brief
1. EIPs were considered
    - EIPs were discussed in All Core Devs calls, with priority given when an author was in attendance for a call.
    - EIPs were split into clusters by scope to facilitate discussion
    - Discussions in the Ethereum Magicians forum, AllCoreDevs gitter
2. The EIPs were reviewed and ultimately classified as:
    - Desired and ready to go into a fork. These were 'accepted'
    - Desired but not ready to go into a fork. These were were 'tentatively accepted' with the intention of including them in the fork-after-istanbul (Berlin fork, see below)
    - Not desired due to fundamental issues including being withdrawn by the author. These were rejected indefinitely.
3. Implementations and testing finalised
4. Ropsten testnet fork planned to give one month between testnet and mainnet forks.
5. Mainnet fork planned
6. The 'tentatively accepted' EIPs to be included in the next fork (Berlin fork)

# Context

Previous hard fork details are summarised in this stack exchange question [here](https://ethereum.stackexchange.com/questions/13014/please-provide-a-summary-of-the-ethereum-hard-forks)

| Fork number | Block number | Date | Name |
|---|---|---|---|
|0|1|2015-07-30|Frontier|
|1|200000|2015-09-07|Frontier Thawing|
|2|1150000|2016-03-14|Homestead|
|3|1920000|2016-07-20|DAO Fork|
|4|2463000|2016-10-18|Tangerine Whistle|
|5|2675000|2016-11-22|Spurious Dragon|
|6|4370000|2017-10-16|Byzantium|
|7|7280000|2019-02-28|Constantinople|
|8|9069000|2019-12-04 ([tentative](https://twitter.com/TimBeiko/status/1190269448621633536))|**Istanbul**|
|9|TBD|2020-06 (tentative)|Berlin (Devcon location)|
|10|TBD|TBD|London|
|11|TBC|TBC|Devcon names thereafter|


# Timeline
* 2019-01-02 Schedule planned and provisionally accepted in Call #52. See [here](https://github.com/ethereum/pm/issues/66#issuecomment-450840440).
* 2019-04-17 (Wed-Thurs) CoreDev planning meeting in Berlin, [details on EthMagicians](https://ethereum-magicians.org/t/istanbul-eth1x-roadmap-planning-meeting-april-17th-18th-in-berlin/2899)
* 2019-05-17 (Fri) hard deadline to accept proposals for “Istanbul”
* 2019-07-19 (Fri) soft deadline for major client implementations
* 2019-07 CoreDev planning meeting proposed
* 2019-08-14 (Wed) projected date for testnet network upgrade (Ropsten, Görli, or ad-hoc testnet) **Delayed due to EIP implementation and testing**
* 2019-xx-xx Ropsten testnet fork
* 2019-10-(8th to 11th) DevCon5, Osaka Japan
* 2019-10-16 (Wed) Initial projected date for mainnet upgrade (“Istanbul”)
* 2019-12-08 Mainnet upgrade ("Istanbul")

# Proposals

Official status of accepted EIPs (in the hard fork meta-EIP) [here](https://eips.ethereum.org/EIPS/eip-1679).

Magicians Discussion thread for the fork meta-EIP [here](https://ethereum-magicians.org/t/hardfork-meta-istanbul-discussion/3207). EIPs have individual discussion threads (listed in the EIP), usually in the magicians forum [here](https://github.com/ethereum/EIPs)

Ethereum Cat Herders tracking page [here](https://github.com/orgs/ethereum-cat-herders/projects/2)

James Hancock has created an automated Google Sheet that covers additional milestones [here](https://docs.google.com/spreadsheets/d/1Mgo7mJ6b6wimUwafsMo1l-b44uec28E_Hq8EQ7YdeEM/edit#gid=0)


## Proposal History

### Entire original list of EIPs proposed for consideration

38 EIPs were proposed in total. After initial discussions in various forums, they were informally/tentatively sorted into groups based a combination of support, clarity, implementation, testing.
- 12 Probable (152, 1108, 1380, 1702, 1706, 1803, 1848, 1884, 1930, 1962, 2028, 2200)
- 8 Possible (615, 663, 1109, 2046, 1283, 1344, 1965, 2045)
- 10 Less likely (1057, 1352, 1559, 2014, 2025, 2026, 2027, 2029, 2031, 2035)
- 8 Not likely (689, 1707, 1712, 1829, 1891, 1959, 1985, 2024)

### 6 EIPs 'Accepted' (for inclusion in Istanbul)

- EIP-152: Add Blake2 compression function F precompile
- EIP-1108: Reduce alt_bn128 precompile gas costs
- EIP-1344: Add ChainID opcode
- EIP-1884: Repricing for trie-size-dependent opcodes
- EIP-2028: Calldata gas cost reduction
- EIP-2200: Rebalance net-metered SSTORE gas cost with consideration of SLOAD gas cost change

### 8 EIPs 'Tentatively Accepted' (for inclusion in Berlin, but not Istanbul)

- EIP-663: Unlimited SWAP and DUP instructions
- EIP-1057: ProgPoW, a Programmatic Proof-of-Work
There is a pending audit, above and beyond standard security considerations, that should be evaluated prior to inclusion.
- EIP-1380: Reduced gas cost for call to self
- EIP-1702: Generalized account versioning scheme
- EIP-1962: EC arithmetic and pairings with runtime definitions
replaces EIP-1829
- EIP-1985: Sane limits for certain EVM parameters
- EIP-2045: Particle gas costs for EVM opcodes
- EIP-2046: Reduced gas cost for static calls made to precompiles

### 23 EIPs 'Rejected/Withdrawn' (not for inclusion)

- EIP-615: Subroutines and Static Jumps for the EVM - Withdrawn
- EIP-1109: PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)
requirement of EIP-1962
- EIP-1283: Net gas metering for SSTORE without dirty maps
replaced by EIP-2200
- EIP-1352: Specify restricted address range for precompiles/system contracts
- EIP-1559: Fee market change for ETH 1.0 chain
- EIP-1706: Disable SSTORE with gasleft lower than call stipend
replaced by EIP-2200
- EIP-1803: Rename opcodes for clarity
- EIP-1829: Precompile for Elliptic Curve Linear Combinations
replaced by EIP-1962
- EIP-1930: CALLs with strict gas semantic. Revert if not enough gas available.
- EIP-1959: New Opcode to check if a chainID is part of the history of chainIDs
- EIP-1965: Method to check if a chainID is valid at a specific block Number
- EIP-2014: Extended State Oracle - Withdrawn
- EIP-2025: Funding Eth1.x with Developer Block Rewards - Withdrawn
- EIP-2026: State Rent H - Fixed Prepayment for accounts
- EIP-2027: State Rent C - Net contract size accounting
- EIP-2029: State Rent A - State counters contract
requirement of EIP-2031
- EIP-2031: State Rent B - Net transaction counter
- EIP-2035: Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs

Referenced in discussions for the fork but not formally in the Istanbul meta-EIP, and not included in Istanbul:
- EIP-689: Address Collision of Contract Address Causes Exceptional Halt
- EIP-1707: Use Version Byte Prefix for Contract Account Versioning
- EIP-1712: Disallow Deployment of Unused Opcodes
- EIP-1848: Fork Names Standard 
- EIP-1891: Contract-based Account Versioning
- EIP-2024: Proposal for supporting Blake2b and Blake2s

### Analysis of themes discussed versus included

Below are some themes that were among the discussed potential changes.

- State rent: Desired but not ready fo Istanbul
- EVM stack operation overhaul (EIP-615): Desired in theory, but complexity, implications for tooling and timeframe overwhelming. Withdrawn by author after a multi-year period of consideration. A similar EIP may be proposed in the future by other authors. An EVM stack call optimisation is on the proposed list for the Berlin fork.
- Account versioning: Initially highly favoured, largely because it was required for EIP-615. Then without a specific use case in mind it was thought that if needed a tailored solution should be implemented to ensure functionality is as desired. While still on the list for Berlin, it is up for discussion as to whether it will go ahead.
- Elliptic curves: Some specific curves implemented, with more general curve solutions still desired by community and left to be polished for the Berlin fork.
- Proof Of Work change: After long community discussion, a proof of work change will go ahead once auditing is complete and any issues rectified.
- Gas calculation granularity: Creating a system that will enable more precise gas costing is on the list proposed changes for the Berlin fork.

---------

### Individual EIP notes

<div align="center">

| EIP | Title | Status | Status note | See discussion cluster |
|-|- |-|-|--------|-|
|[EIP-152](https://github.com/ethereum/EIPs/pull/2129)|Blake 2b 'F' Precompile (Matt Luongo)|Accepted (Istanbul) |-|Elliptic curve|
|[EIP-615](https://eips.ethereum.org/EIPS/eip-615)|Subroutines and Static Jumps for the EVM|Withdrawn|Mix of issues: complexity, time shortage, funding and impact on tooling|Account versioning|
|[EIP-663](https://eips.ethereum.org/EIPS/eip-663)|Unlimited SWAP and DUP instructions|Tentatively accepted (Berlin)|Addresses similar stack-access problem as 615 (withdrawn). Three technical options are presented (needs refining). Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)  | Account versioning |
|[EIP-689](https://eips.ethereum.org/EIPS/eip-689)|Address Collision of Contract Address Causes Exceptional Halt|Rejected/Withdrawn (not proposed)|[Not needed](https://youtu.be/lF_XxqxgVuA?t=283). No hard fork required and is covered by [issue 684](https://github.com/ethereum/EIPs/issues/684)|Independent|
|[EIP-1057](https://eips.ethereum.org/EIPS/eip-1057)|ProgPoW, a Programmatic Proof-of-Work|Tentatively accepted (Berlin) in decision [66.3](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|Pending audit results|Independent|
|[EIP-1108](https://eips.ethereum.org/EIPS/eip-1108)|Reduce alt_bn128 precompile gas costs|Accepted (Istanbul)| Accepted in decision [66.5](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|Elliptic curve|
|[EIP-1109](https://eips.ethereum.org/EIPS/eip-1109)|PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)|Rejected/Withdrawn|Conflict with 2046 (which is Tentatively accepted (Berlin))|Elliptic curve|
|[EIP-1283](https://eips.ethereum.org/EIPS/eip-1283)|Net gas metering for SSTORE without dirty maps|Rejected/Withdrawn|Replaced by newer verision, EIP-2200 (Accepted)|Storage writing|
|[EIP-1344](https://eips.ethereum.org/EIPS/eip-1344)|ChainID opcode|Accepted (Istanbul)|Accepted in decision [66.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md). Complements 1965 (which is rejected/withdrawn)|Chain metadata|
|[EIP-1352](https://eips.ethereum.org/EIPS/eip-1352)|Specify restricted address range for precompiles/system contracts|Rejected/Withdrawn|Rejected in decision [67.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md) due to lack of champion. No consensus on whether precompiles should be addressed via a range (1352) or by client-based-lists |Elliptic curve|
|[EIP-1380](https://eips.ethereum.org/EIPS/eip-1380)|Reduced gas cost for call to self|Tentatively accepted (Berlin)|Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|Independent|
|[EIP-1559](https://eips.ethereum.org/EIPS/eip-1559)|Fee market change for ETH 1.0 chain|Withdrawn| Not completed in time. Concerns about effect on [transaction propagation](https://youtu.be/lF_XxqxgVuA?t=4506). Withdrawn in decision [67.4](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md) due to lack of champion.|Independent|
|[EIP-1702](https://eips.ethereum.org/EIPS/eip-1702)| Generalized Account Versioning Scheme|Tentatively accepted (Berlin)|Design-1 variant was been accepted in decision [63.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2063.md). Concerns about what specifically this is needed for.|Account versioning|
|[EIP-1706](https**://eips.ethereum.org/EIPS/eip-1706)|Disable SSTORE with gasleft lower than call stipend|Rejected/Withdrawn|Replaced by EIP-2200 (Accepted)|Storage writing|
|[EIP-1707](https://github.com/ethereum/EIPs/pull/1707)|Use Version Byte Prefix for Contract Account Versioning|Rejected/Withdrawn (not proposed)|Superceded by 1702 (which is tentatively accepted (Berlin))|Account versioning|
|[EIP-1712](https://github.com/ethereum/EIPs/pull/1712)|Disallow Deployment of Unused Opcodes|Rejected/Withdrawn (not proposed)|Superceded by 1702 (which is tentatively accepted (Berlin))|Account versioning|
|[EIP-1803](https://eips.ethereum.org/EIPS/eip-1803)|Rename opcodes for clarity|Rejected/Withdrawn|Rejected in decision [67.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md) due to lack of champion.|Independent|
|[EIP-1829](https://eips.ethereum.org/EIPS/eip-1829)|Precompile for Elliptic Curve Linear Combinations|Rejected|Superceded by 1962 (which is Tentatively accepted (Berlin)). Rejected in decision [66.7](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|Elliptic curve|
|[EIP-1848](https://github.com/ethereum/EIPs/pull/1848)|Fork Names Standard|Rejected/Withdrawn (not proposed)|-|Independent|
|[EIP-1884](https://eips.ethereum.org/EIPS/eip-1884)|Repricing for trie-size-dependent opcodes|Accepted (Istanbul)| Accepted in decision [68.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2068.md)|Storage gas cost|
|[EIP-1891](https://github.com/ethereum/EIPs/pull/1891)|Contract-based Account Versioning|Rejected/Withdrawn (not proposed)|Superceded by 1702 (which is tentatively accepted (Berlin))|Account versioning|
|[EIP-1930](https://eips.ethereum.org/EIPS/eip-1930)|CALLs with strict gas semantic. Revert if not enough gas available|Rejected/Withdrawn|-|Elliptic curve|
|[EIP-1959](https://eips.ethereum.org/EIPS/eip-1959)|New Opcode to check if a chainID is part of the history of chainIDs|Withdrawn by Author in decision [64.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2064.md)|Superceded by 1965 (which is rejected/withdrawn)|Chain metadata|
|[EIP-1962](https://eips.ethereum.org/EIPS/eip-1962)|EC arithmetic and pairings with runtime definitions|Tentatively accepted (Berlin) in decision [66.5](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|-|Elliptic curve|
|[EIP-1965](https://eips.ethereum.org/EIPS/eip-1965)|Method to check if a chainID is valid at a specific block Number|Rejected/Withdrawn|-|Chain metadata|
|[EIP-1985](https://eips.ethereum.org/EIPS/eip-1985)|Sane limits for certain EVM parameters|Tentatively accepted (Berlin)|Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|Independent|
|[EIP-2014](https://eips.ethereum.org/EIPS/eip-2014)|Extended State Oracle|Rejected/Withdrawn|-|Chain metadata|
|[EIP-2024](https://github.com/ethereum/EIPs/pull/2024)|Proposal for supporting Blake2b and Blake2s|Rejected/Withdrawn (not proposed)|Accepted in decision [63.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2063.md), but then superceded by EIP-152|Elliptic curve|
|[EIP-2025](https://github.com/ethereum/EIPs/pull/2025)|Funding ETH1.X through a Developer Block Reward for 18 Months|Rejected/Withdrawn|Strong community resistance, concerns over governance mechanism and neutrality|Independent|
|[EIP-2026](https://eips.ethereum.org/EIPS/eip-2026)|State Rent H - Fixed Prepayment for accounts|Rejected/Withdrawn|Not ready in time|State rent|
|[EIP-2027](https://eips.ethereum.org/EIPS/eip-2027)|State Rent C - Net contract size accounting|Rejected/Withdrawn|Not ready in time|State rent|
|[EIP-2028](https://eips.ethereum.org/EIPS/eip-2028)|Calldata gas cost reduction| Accepted (Istanbul)|Accepted in decision [66.5](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|Independent|
|[EIP-2029](https://eips.ethereum.org/EIPS/eip-2029)|State Rent A - State counters contract|Rejected/Withdrawn|Not ready in time|State rent|
|[EIP-2031](https://eips.ethereum.org/EIPS/eip-2031)|State Rent B - Net transaction counter|Rejected/Withdrawn|Not ready in time|State rent|
|[EIP-2035](https://eips.ethereum.org/EIPS/eip-2035)|Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs|Rejected/Withdrawn|-|Storage gas cost|
|[EIP-2045](https://eips.ethereum.org/EIPS/eip-2045)|add EIP for fractional gas costs|Tentatively accepted (Berlin)|Geth/Parity to be guided to implement EVM-One changes, benchmark and determine specific specific parameters for the EIP. Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)	|Storage gas cost|
|[EIP-2046](https://eips.ethereum.org/EIPS/eip-2046)|Reduced gas cost for static calls made to precompiles|Tentatively accepted (Berlin)|Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|Elliptic curve|
|[EIP-2200](https://github.com/ethereum/EIPs/pull/2200)|Rebalance net-metered SSTORE gas cost with consideration of SLOAD gas cost change|Accepted (Istanbul)|Accepted in decision [66.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md). Is an update version of (and replaces) 1283|Storage writing|

</div>

Some EIPs are complementary and some are mutually exclusive improvements that deprecate other proprosals. Below is a rough clustering to highlight these relationships. 


### Focused Co-ordination Discussions

To reduce the load on discussing each EIP independently in the dev calls, some EIP coordination happened in AllCoreDevs gitter [here](https://gitter.im/ethereum/AllCoreDevs) during the first week of June 2019.

The clusters (expanded below) were:
- Elliptic curve cluster
- Account versioning cluster
- Chain metadata cluster
- Storage gas cost cluster
- Storage writing cluster
- Independent / not clustered

<img src="https://docs.google.com/drawings/d/e/2PACX-1vS7t5kwTrxL3zja2hLIPcNchPtBoXBeSxWNG8-tm5vlGPV4XycY7PMQDWKQGRXd_vwEPLO8dIbPR7EH/pub?w=2762&amp;h=1430">

Link to Google Drawing [here](https://docs.google.com/drawings/d/14vSgSGLkr9iPLTpOuZrtSoGyspHYDPh9ue6Ki4hrj54/)


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
- [LibSNARK](https://github.com/scipr-lab/libsnark/tree/f7c87b88744ecfd008126d415494d9b34c4c1b20) which uses edwards 'ed-', bn128 or alt_bn128 curves. Edwards curves are made cheaper with 1829. The alt_bn128 curve is are made cheaper with 1108.
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
- [152 Blake 2b 'F' Precompile](https://github.com/ethereum/EIPs/pull/2129) (Matt Luongo)
- [1829 Precompile for Elliptic Curve Linear Combinations](https://eips.ethereum.org/EIPS/eip-1829) (Remco Bloemen)
- [1962 EC arithmetic and pairings with runtime definitions](https://eips.ethereum.org/EIPS/eip-1962) (Alex Vlasov)
- [1109 PRECOMPILEDCALL opcode (Remove CALL costs for precompiled contracts)](https://eips.ethereum.org/EIPS/eip-1109) (Jordi Baylina)
- [1108 Reduce alt_bn128 precompile gas costs](https://eips.ethereum.org/EIPS/eip-1108) (Antonio Salazar Cardozo, Zachary Williamson)
- [1930 CALLs with strict gas semantic. Revert if not enough gas available](https://eips.ethereum.org/EIPS/eip-1930) (Ronan Sandford)
- [2024 Proposal for supporting Blake2b](https://github.com/ethereum/EIPs/pull/2024) (James Hancock)
- [2046 Reduced gas cost for static calls made to precompiles](https://eips.ethereum.org/EIPS/eip-2046) (Alex Beregszaszi)

#### Key concepts and EIP interactions

**Introduce new curves using elliptic curve arithmetic with either 1962 (preferred) or 1829**

Both 1829 and 1962 allow for new curves to be added later without waiting for specific precomiples to be included in hard forks. 1829 Allows a class of eliptic curves (Edward curves) to be supported through a precompile for linear combinations. 1962 is a precompile that extends and formalises 1829. 1962 features (as compared to 1829) three main differences:
- Operation on arbitrary-length modulus (up to some upper-limit) for a base field and scalar field of the curve
- Pairing operations are introduced
- Different ABI due to variable parameter length

There were [no supporting arguments in a recent discussion](https://gitter.im/ethereum/AllCoreDevs?at=5cf52f58ff3f016baa9a64c7) for 1829, and 1962 is progressing well, so 1829 will not be needed. 1962 requires either 1109 or 2046 to make calls economically viable (see below).

**How to define a precompile? (address range with 1352 vs client-based lists of known precompiles)**

1352 is still a **maybe** and the decision of "how do we define what a preompile is" is up for discussion. While it creates a nice range for defining what precompiles are, which [may help](https://gitter.im/ethereum/AllCoreDevs?at=5cf543c5702b7e5e7621ed0f) with static analysis, there are some serious [concerns on FEM](https://ethereum-magicians.org/t/eip-1352-restricted-address-range-for-precompiles-system-contracts/1151/26) about safety. It was clarified that 1352 is not required explicitly by either 1109 or 2046, so either of those can be chosen, but they may need to be modified to be clear about how the define a precompile. **Action required**: Decide if precompiles should be defined by range (push forward with 1352) or client based [lists](https://gitter.im/ethereum/AllCoreDevs?at=5cf53cd06f530d3b612d9c96) (shelve 1352).

**Make precompile call costs cheaper, either by modifying an existing opcode (2046) or introducing a new opcode (1109)**

The goal is to make precompiles cheaper. Both EIPs seek to make 1108, 2024 and 1962 cheaper by reducing the cost of calling a precompile. The decision of 1109 vs 2046 was **undecided**. The [options](https://gitter.im/ethereum/AllCoreDevs?at=5cf53d0bfaac6439343331a3) for calling precompiles are either to create a new opcode (choose 1109) or to modify the semantics of STATICCALL if the destination is a precomile. **Action required**: Decide if we prefer a new opcode or to modify an old opcode.

**Specific curve optimisations:**

There is a lot of interest in enabling immediate use of specific curves. Alt_bn128 is enabled by 1108. 1108 also supplements 1829 which reduces the cost of addition, multiplication and and pairing checks. 

Blake2b is enabled by 2024 which introduces a specific precompile for Blake2b for immediate use. Both 1108 and 2024 can coexist with 1962 [without issue](https://gitter.im/ethereum/AllCoreDevs?at=5cf4d34a6fc5846bab533deb)

In ACD call 63 (45min41s), James Preswitch outlined that 2024 is superceded by a new [implementation](https://github.com/ethereum/EIPs/pull/2129) with F-compression, with smaller codebase changes, with less work required by client teams. Maintained by Keep, who have implemented in Geth. It is faster than the dedicated Blake2b 2024. The 2s curve could be a nice-to-have, for future ZCash-Ethereum interop, but at the moment has no implementation and maybe could go in the April 2020 hard fork. 

**DOS attack mitigation**

There was a [discussion](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/8) about DOS attacks from calls that result in disk loading being too cheap. It seems that as long as the opcode being made cheaper only applies to precompiles, then [there is no risk](https://ethereum-magicians.org/t/eip-1109-remove-call-costs-for-precompiled-contracts/447/9). 

1930 Adds the ability to make calls with specific amounts of gas, with a revert endpoint, through new variants of STATICCALL, DELEGATECALL and CALL. This [may benefit EIPs](https://gitter.im/ethereum/AllCoreDevs?at=5cf576215de053468b08b9b8) that modify CALL/STATICCALL behaviour. The winner out of 1109 vs 2046 will need to be checked against 1930 to ensure behaviour is as expected.  

#### Elliptic Curve Cluster Outcome
- Prepare for Istanbul: 152 and 1108.
- Prepare for Berlin: 1962 and 2046.
- Shelve indefinitely: 1109, 1829 and 2024.


### **Storage writing cluster**


#### Key benefits:
- 1283 allows multiple write operation within a single call frame, allowing re-entry locks and multi-sends which are important for synchronus cross-dapp interactions..

#### Relevant EIPs:
- [1283 Net gas metering for SSTORE without dirty maps](https://eips.ethereum.org/EIPS/eip-1283) (Wei Tang). Clients already have implementations. The spec has been reviewed by many people. Previously had a re-entrancy bug [caused by contracts assuming long term stability of gas costs](https://ethereum-magicians.org/t/immutables-invariants-and-upgradability/2440) which is now addressed with either **account versioning** or with 1706. There have been in-depth about choices of different net gas metering options (EIP-1087, EIP-1153, EIP-1283).
- [2200](https://github.com/ethereum/EIPs/pull/2200) Rebalance net-metered SSTORE gas cost with consideration of SLOAD gas cost change. This EIP is an updated version of 1283.
- [1706 Disable SSTORE with gasleft lower than call stipend](https://eips.ethereum.org/EIPS/eip-1706) (Alex Forshtat, Yoav Weiss). 1706 is a required for 1832 to be compatible with many existing contracts if no account versioning is implemented.

#### Key concepts:
- Net gas metering is a [desired](https://gitter.im/ethereum/AllCoreDevs?at=5cfa29c1cea8295279090c00) feature. This can be provided with 1283 in a timely fashion without depending on the State Rent EIPs, with or without the use of account versioning.
- Net gas metering significantly reduces the gas cost for mutex and multi-step token transfers, which are necessary for synchronous cross dapp interactions. Benefits include improving [uniswap](https://gitter.im/ethereum/AllCoreDevs?at=5cfa77c8481ef4167be72d39).
- Even if account versioning goes ahead and 1706 is not explicitly required, it is simple to implement and would avoid future issues with repricing as noted [here](https://gitter.im/ethereum/AllCoreDevs?at=5cfa2cb465392c3b60d43ba6).
- Net gas metering would [not interfere](https://gitter.im/ethereum/AllCoreDevs?at=5cfa29c1cea8295279090c00) with State Rent EIPs, or complicate their designs. First, net gas metering can be implemented with account versioning. Second, even if net gas metering is implemented without account versioning, it can be easily toggled on or off many times on-chain without hugely affecting existing contracts. Given 1283 is strongly desired, implementing it even if metering is planned for State Rent seems preferred.
- It can be [beneficial](https://gitter.im/ethereum/AllCoreDevs?at=5cfa2e6a702b7e5e76439672) to implement net gas metering without account versioning, because existing contracts can also receive gas reduction.

#### Key decisions:
- Are there any opposed to implementing 1706 even if not explicitly required by 1283 (that is, if account versioning goes ahead)? If no, people need to review the 1706 [implementation](paritytech/parity-ethereum#10191) (the original fix for 1283).


#### Storage Writing Cluster Outcome
- Prepare for Istanbul: 2200
- Prepare for Berlin: None
- Shelve indefinitely: 1283, 1706


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
- 663 can coexist with 615, as discussed by [Greg](https://gitter.im/ethereum/AllCoreDevs?at=5d085a3ed1b1df620d1937be). Previous opinion was that 663 is [made redundant](https://github.com/ethereum/EIPs/pull/663#issuecomment-318838695) by 615 through the use of [PUTLOCAL and GETLOCAL](https://ethereum-magicians.org/t/eip-615-subroutines-and-static-jumps-for-the-evm/2728/33). It was also thought initially that it would [break safety guarantees](https://gitter.im/ethereum/AllCoreDevs?at=5cf7f34bf31ba302588e445a) if co-implemented with 615, though not the case, as long as 663 is not 'unlimited', but limited ot the stack frame.


Three account versioning proposals, only one must be selected
- **1702 (preferred)**. The EIP has two variants, with the second variant being preferred (In the EIP see under Specification -> Contract Deployment -> [Alternative Design](https://eips.ethereum.org/EIPS/eip-1702))
- 1707 + 1712 (likely not for istanbul). Version as RLP item based on code header prefix. Possibly backward incompatible.
- 1891 (likely not for Istanbul). Store version in a dedicated contract, and [use new opcodes VCREATE/VCREATE2 to get version](https://github.com/ethereum/EIPs/pull/1891/files). Compared to other two solutions will have worse performance (extra to call to state trie), but is less complex and benefits by: 1) Allowing account state format to stay the same, 2) allowing precompile invocation to stay the same and 3) by preventing forging of version bytes.

**1702 flavours: 1 with-optional-code-prefix (Preferred) and 2 with-compulsory-code-prefix (not preferred)**
- Design 1: A contract can only deploy subcontract with the same version.Requires either only allowing deploying "newest" version, or achange in RLP structure in contract creation transactions.
- Design 1 variant makes contract deployment transaction deploys a contract family, and only allow newest account version to be deployed at root. Once we deploy newer versions (like eWASM), older versions (like EVM) should not be able to be deployed again. This is just architecturally simple. EIP-1702 author Wei Tang slightly prefers this, and the 615 team is okay with this design (as per ACD call #63 1hr6mins).
- Design 2: All version that is not zero requires a code prefix (such as\0asm). It can be variable length, but must be unique.
- Design 2 variant allows all versions to be deployed, but it requires contract header prefix for all subsequent account versions. This variant [was previously preferred](https://gitter.im/ethereum/AllCoreDevs?at=5cf6733c82e5c67322287ece) by the 615 team and had [support](https://gitter.im/ethereum/AllCoreDevs?at=5cf68498f3a60a79a451a78b). However in subsequent discussion between Wei and Greg, Design 1 was decided to be preferred.

#### Account Versioning Cluster Outcome
- Prepare for Istanbul: None
- Prepare for Berlin: 663 and 1702 (Design-#1).
- Shelve indefinitely: 615, 1891, 1707 and 1712.


### **Storage gas cost cluster**

#### Key benefits:
Some opcodes are mispriced, and by repricing them more transations could fit into blocks.
A separate new counter that counts gas with more granularity prepares clients for how eWASM contracts meter gas.

#### Relevant EIPs:
- [1884 Repricing for trie-size-dependent opcodes](https://eips.ethereum.org/EIPS/eip-1884) (Martin Holst Swende)
- [2035 Stateless Clients - Repricing SLOAD and SSTORE to pay for block proofs](https://eips.ethereum.org/EIPS/eip-2035) (Alexey Akhunov)
- [2045 add EIP for fractional gas costs](https://eips.ethereum.org/EIPS/eip-2045) (Casey Detrio)

#### Key concepts
**Match gas cost with CPU-time cost**: Current gas costs do not reflect the true CPU cost of operations. In particular, SLOAD and BALANCE are overpriced. 1884 Increases SLOAD and BALANCE gas costs, to properly reflect real relative CPU-time cost. A new opcode SELFBALANCE is also introduced.

**Increase throughput without state bloat**: To increase transaction throughput the price of computation opcodes (e.g ADD, SUB, MUL etc.) could be decreased by up to a factor of 10. The EIP leaves the gas cost of other opcodes the same (e.g those that affect the state size such as SSTORE, CREATE). To lower the cost of these computational opcodes, which are already priced close to 1 (the minimum possible value), the idea is to allow fractions of gas. 2045 introduces a new gas counter `particles` which is an optional feature that some developers may chose to use when hunting for more optimised contracts. Optimisations in [evmone](https://github.com/ethereum/evmone) could be implemented in Geth and Parity to reduce the real CPU time for these opcodes, allowing for [the benchmarked](https://github.com/ewasm/benchmarking#evm-benchmarks-2019-05-23) ~10x reduction in some gas costs.

#### EIP interactions
Other EIPs that affect storage gas costs might be:
- 2035 Part of the **state rent** roadmap, also increases SLOAD in order to allow better block proof transmission. 

#### Key questions
- Can geth and parity implement the evmone optimisations?
- What are the real costs of the computational opcodes in Geth and Parity after optimisations?
- What precise values should 2045 have for each computational opcode (ADD, SUB, MUL..), post-optimisations?

#### Storage Gas Cost Cluster Outcome
- Prepare for Istanbul: 1884
- Prepare for Berlin: 2045
- Shelve indefinitely: 2035

### **Chain metadata cluster**

#### Relevant EIPs:
- [1965 Method to check if a chainID is valid at a specific block number](https://eips.ethereum.org/EIPS/eip-1965) (Ronan Sandford)
- [1959 New Opcode to check if a chainID is part of the history of chainIDs](https://eips.ethereum.org/EIPS/eip-1959) (Ronan Sandford)
- [1344 ChainID opcode](https://eips.ethereum.org/EIPS/eip-1344) (Richard Meissner, Bryant Eisenbach)
- [2014 Extended State Oracle](https://eips.ethereum.org/EIPS/eip-2014) (Alex Beregszaszi)

#### Key concepts:
1965 Adds a precompile to get the ChainID at a specific block number. This supercedes 1959, which introduces ChainID as a new opcode, but likely has reduced fork freedom.

1344 introduces ChainID via an opcode. Could theoretically co-exist with 1965, but provides similar functionality. Safe from replay vulnerabilities, but has additional considerations (as noted in the EIP rationale). There may be some utility in using both 1344 and 1965 at the time of a hard fork to allow transactions to traverse the fork more cleanly, as discussed in the [forum](https://ethereum-magicians.org/t/eip-1344-add-chain-id-opcode/1131/92)

2014 Introduces an extensible contract system to bring more data to smart contracts, including block hashes and chain identifiers, using the contract ABI encoding. Might be used with 1965 or 1959 to check the validity of the chain identifier for a block. There are concerns in the EIP discussion [thred](https://ethereum-magicians.org/t/eip-2014-extended-state-oracle/3301/5) that including a method for chain ID in this EIP is complex and not wise.

#### Key Questions
- Should 2014 be modified to exclude the method for ChainID?
- Is there anyone who thinks that 1344 is not needed, given that 1965 is going ahead? 

#### Chain Metadata Cluster Outcome
- Prepare for Istanbul: 1344
- Prepare for Berlin: None
- Shelve indefinitely: 1959, 1965 and 2014.

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

#### State Rent Cluster Outcome
- Prepare for Istanbul: None
- Prepare for Berlin: None
- Shelve indefinitely (until ready): 2035, 2026, 2027, 2029 and 2031 

# Post-Istanbul

The next fork will be called [Muir Glacier](eth.wiki/roadmap/muir_glacier) and will address the difficulty bomb.
