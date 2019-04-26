<!-- TITLE: Istanbul -->
<!-- SUBTITLE: October 2019 Planned Ethereum Network Upgrade -->

# Timelines
* 2019-04-17 (Wed-Thurs) CoreDev planning meeting in Berlin, [details on EthMagicians](https://ethereum-magicians.org/t/istanbul-eth1x-roadmap-planning-meeting-april-17th-18th-in-berlin/2899)
* 2019-05-17 (Fri) hard deadline to accept proposals for “Istanbul”
* 2019-07-19 (Fri) soft deadline for major client implementations
* 2019-08-14 (Wed) projected date for testnet network upgrade (Ropsten, Görli, or ad-hoc testnet)
* 2019-10-16 (Wed) projected date for mainnet upgrade (“Istanbul”)

# Proposals
* [EIP 1679](https://eips.ethereum.org/EIPS/eip-1679) is the Istanbul Hardfork tracking Meta EIP. See [improvements to Hardfork Meta EIP233](https://github.com/ethereum/EIPs/pull/1852)


* [EIP 1829](https://eips.ethereum.org/EIPS/eip-1829) Precompile for Elliptic Curve Linear Combinations.
* [EIP 615](https://eips.ethereum.org/EIPS/eip-615) Static Jumps and Subroutines
* [EIP 1057](https://eips.ethereum.org/EIPS/eip-1057) ProgPoW, a Programmatic Proof-of-Work
* [EIP-1344](https://eips.ethereum.org/EIPS/eip-1344) Add ChainID opcode
* [EIP-1352](https://eips.ethereum.org/EIPS/eip-1352) Specify restricted address range for precompiles/system contracts
* [EIP-689](https://eips.ethereum.org/EIPS/eip-689) Address Collision of Contract Address Causes Exceptional Halt
* [EIP 1884](https://github.com/ethereum/EIPs/blob/dcc573e74adc0e6dd25821ddaabf862e8f85e107/EIPS/eip-1884.md) Reprice Opcodes + optional new opcode - [Discuss](https://ethereum-magicians.org/t/opcode-repricing/3024)


Virgil mentioned that [EIP 665](https://eips.ethereum.org/EIPS/eip-665) Adding precompiles for Ed25519 is not needed, because 1829 is a superset and supports the needs.

## Draft in Progress
These items are not yet merged as Drafts. See EIP-1 for template and markdown format and submit PRs.

* [EIP 1559](https://github.com/ethereum/EIPs/issues/1559) Fee market change - [Discuss](https://ethereum-magicians.org/t/eip-1559-fee-market-change-for-eth-1-0-chain/2783) - Proposed by Vitalik / Eric
* [EIP 152](https://github.com/ethereum/EIPs/issues/152) BLAKE2b `F` Compression Function Precompile - [Discuss](https://ethereum-magicians.org/t/istanbul-eth1x-roadmap-planning-meeting-april-17th-18th-in-berlin/2899/21) - Being worked on by Virgil
* [EIP 1803](https://github.com/ethereum/EIPs/pull/1803) Rename opcodes for clarity
* [EIP 663](https://eips.ethereum.org/EIPS/eip-663) Unlimited SWAP and DUP instructions

_Follow along All Core Dev calls and the [EIPs repo](https://github.com/ethereum/EIPs)._


currently new updates
_Newest at the top, likely EthCatHerders repo / Github project will be source of updates going forward_

* Discussed on [Core Devs call 57](https://github.com/ethereum/pm/issues/83), no one disagreed with current timelines
* There is a WIP [Client Tracker](/roadmap/istanbul/tracker)
* EthCatHerders organizing, see [PM repo](https://github.com/ethereum-cat-herders/PM/tree/master/Hard%20Fork%20Planning%20and%20Coordination), Joseph DeLong point of contact for Istanbul 
* Afri proposed the [schedule on the Jan 4th All Core Devs call](https://github.com/ethereum/pm/issues/66#issuecomment-450840440) where it was provisionally accepted

# Discussion
## Proposed: Security Review Period
Should we add a security review period? Let's say 4 weeks needed minimum once people responsible for review have the EIPs available, so maybe 2019-06-21 for first security review / reports? [Discuss on EthMagicians](https://ethereum-magicians.org/t/security-review-period-for-hardfork-roadmap/2721)

