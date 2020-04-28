---
title: Berlin
description: Notes about the hard fork upgrade following Istanbul
published: true
date: 2019-08-31T06:20:37.853Z
tags: 
---

The [Etherum 1.x](/eth1) page is a good starting point for an overview of Working Groups and areas of focus.

# Philosophy

Regular small hard forks allow upgrades to be included in more timely and manageable way that large infrequent forks, as described [here](https://ethereum-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28) 

The fork will ideally follow an *EIP-centric* approach outlined [here](https://notes.ethereum.org/@holiman/S1ELAYY7S?type=view). This approach will allow EIPs to mature independently of forking schedule. When mature, they can be added to the next scheduled fork.

Steps for EIPs:
1. Endorsement (by major clients, developers and community stakeholders)
2. Implementation (merged into major clients)
3. Testing
4. Acceptance (Allocate to a specific hard fork)

# TL;DR

- The Berlin fork follows Istanbul 
- Some desired EIPs were not ready for Istanbul, and so were 'tentatively accepted' with the intention of considering them for Berlin
- Smaller frequent forks are preferred, so EIPs that were not 'tentatively accepted' will be considered for the fork after Berlin

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
|8|TBD|TBD|Istanbul|
|9|TBD|TBD|**Berlin**|
|10|TBD|TBD|London|
|11|TBC|TBC|Devcon names thereafter|


# Timeline
Details to follow after Istanbul fork is completed

# Proposals

The proposed EIPs will be derived from the 'Tentatively Accepted' EIPs from the Istanbul Meta-EIP [here](https://eips.ethereum.org/EIPS/eip-1679).

### Starting list ('Endorsed' EIPs)

The following 8 EIPs were 'Tentatively Accepted'
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

### Selection process

Review of the EIPs will be ongoing, those complete the following hurdles will progress
1. Endorsement (Community sentiment, developer agreement)
2. Implementation (merged into major clients)
3. Testing (Including final checks from the testing team)
4. Acceptance (Confirmation that the EIP will specifically go in the Berlin fork)

## Proposal History

This [diagram](https://docs.google.com/drawings/d/1K40GGAcNGjWhe9I0G4AIgGxppgLiL5_gdFcg9lG2YWI/edit?usp=sharing) loosely captures the proposal history for Istanbul and Berlin. Below are some themes that are among the discussed potential changes.

- **EVM stack**: An improvement of the stack operation is proposed, affecting SWAP and DUP instructions
- **Account versioning**: Initially highly favoured in the lead up to Istanbul, largely because it was required for EIP-615. Then without a specific use case in mind it was thought that if needed a tailored solution should be implemented to ensure functionality is as desired. While still on the list for Berlin, it is up for discussion as to whether it will go ahead.
- **Elliptic curves**: Some specific curves implemented, with more general curve solutions still desired by community and left to be polished for the Berlin fork.
- **Proof Of Work change**: After long community discussion, a proof of work change will probably go ahead once auditing is complete and any issues rectified.
- **Gas calculation**: Creating a system that will enable more precise gas costing.

---------

### Individual EIP notes

<div align="center">

| EIP | Title | Status | Status note | Topic |
|-|- |-|-|--------|-|
|[EIP-663](https://eips.ethereum.org/EIPS/eip-663)|Unlimited SWAP and DUP instructions|Proposed|Tentatively raised for Berlin in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)  | EVM stack |
|[EIP-1057](https://eips.ethereum.org/EIPS/eip-1057)|ProgPoW, a Programmatic Proof-of-Work|Proposed|Pending audit results|PoW|
|[EIP-1380](https://eips.ethereum.org/EIPS/eip-1380)|Reduced gas cost for call to self|Proposed|Tentatively raised for Berlin in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|Gas|
|[EIP-1702](https://eips.ethereum.org/EIPS/eip-1702)| Generalized Account Versioning Scheme|Proposed|Design-1 variant was tentatively proposed for Berlin in decision [63.2](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2063.md)|Account versioning|
|[EIP-1962](https://eips.ethereum.org/EIPS/eip-1962)|EC arithmetic and pairings with runtime definitions|Proposed|Tentatively raised for Berlin in decision [66.5](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2066.md)|Elliptic curve|
|[EIP-1985](https://eips.ethereum.org/EIPS/eip-1985)|Sane limits for certain EVM parameters|Proposed|Tentatively accepted in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|EVM stack|
|[EIP-2045](https://eips.ethereum.org/EIPS/eip-2045)|add EIP for fractional gas costs|Proposed| Tentatively proposed for Berlin in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)	|Gas|
|[EIP-2046](https://eips.ethereum.org/EIPS/eip-2046)|Reduced gas cost for static calls made to precompiles|Proposed|Tentatively proposed for Berlin in decision [67.1](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2067.md)|Elliptic curve|


</div>

# Post-Berlin

The next fork will be called London, in keeping with the DevCon location sequence. 

The fork will consist of EIPs mature enough to go in, following the EIP-centric development cycle. Forks will preferentially be small and on-time rather than large and late, with the knowledge that regular forks allow almost-ready EIPs a concrete timeline for incorporation.