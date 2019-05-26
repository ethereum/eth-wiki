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

* [EIP-615](https://eips.ethereum.org/EIPS/eip-615): Subroutines and Static Jumps for the EVM
* [EIP-1057](https://eips.ethereum.org/EIPS/eip-1057): ProgPoW, a Programmatic Proof-of-Work (contingent on positive audit results) - @IfDefElse
* [EIP-1108](https://eips.ethereum.org/EIPS/eip-1108): Reduce alt_bn128 precompile gas costs - @zac-williamson
* [EIP-1283](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1283.md): Net gas metering for SSTORE without dirty maps @sorpass
* [EIP-1344](https://eips.ethereum.org/EIPS/eip-1344): Add ChainID opcode - @fubuloubu
* [EIP-1352](https://eips.ethereum.org/EIPS/eip-1352): Specify restricted address range for precompiles/system contracts
* [EIP 1380](https://eips.ethereum.org/EIPS/eip-1380): Reduced gas cost for call to self - @axic @jacqueswww
* [EIP 1559](https://eips.ethereum.org/EIPS/eip-1559): Fee market change for ETH 1.0 chain
* [EIP-1965](https://eips.ethereum.org/EIPS/eip-1965): Method to check if a chainID is valid at a specific block Number
* [EIP-1702](https://eips.ethereum.org/EIPS/eip-1702): Generalized account versioning scheme - @sorpaas
* [EIP-1706](https://eips.ethereum.org/EIPS/eip-1706): Disable SSTORE with gasleft lower than call stipend
* [EIP 1803](https://eips.ethereum.org/EIPS/eip-1803): Rename opcodes for clarity - @axic
* [EIP 1829](https://eips.ethereum.org/EIPS/eip-1829): Precompile for Elliptic Curve Linear Combinations @remco
* [EIP 1884](https://github.com/ethereum/EIPs/blob/dcc573e74adc0e6dd25821ddaabf862e8f85e107/EIPS/eip-1884.md): Reprice Opcodes + optional new opcode, @holiman - [Discuss](https://ethereum-magicians.org/t/opcode-repricing/3024)
* [EIP 1930](https://eips.ethereum.org/EIPS/eip-1930): CALLs with strict gas semantic. Revert if not enough gas available
* [EIP 2028](https://eips.ethereum.org/EIPS/eip-2028): Calldata gas cost reduction


_Follow along All Core Dev calls and the [EIPs repo](https://github.com/ethereum/EIPs)._


# Updates
_Newest at the top, likely EthCatHerders repo / Github project will be source of updates going forward_

* Reviewed on [Core Devs call 60](https://github.com/ethereum/pm/issues/95), including call for PRs to 1679
* Discussed on [Core Devs call 57](https://github.com/ethereum/pm/issues/83), no one disagreed with current timelines
* There is a WIP [Client Tracker](/roadmap/istanbul/tracker)
* EthCatHerders organizing, see [PM repo](https://github.com/ethereum-cat-herders/PM/tree/master/Hard%20Fork%20Planning%20and%20Coordination), Joseph DeLong point of contact for Istanbul 
* Afri proposed the [schedule on the Jan 4th All Core Devs call](https://github.com/ethereum/pm/issues/66#issuecomment-450840440) where it was provisionally accepted


