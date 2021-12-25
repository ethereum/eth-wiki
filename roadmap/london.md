---
title: London
description: Notes about the hard fork upgrade following Berlin
published: true
date: 2019-08-31T06:09:10.582Z
tags: 
---

The [Etherum 1.x](/eth1/eth1.md) page is a good starting point for an overview of Working Groups and areas of focus.

# Philosophy

Early flagging, discussion and implementation of EIPs for future forks can allow smoother planning.

Regular small hard forks allow upgrades to be included in more timely and manageable way that large infrequent forks, as described [here](https://ethereum-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28) 

The fork will ideally follow an *EIP-centric* approach outlined [here](https://notes.ethereum.org/@holiman/S1ELAYY7S?type=view). This approach will allow EIPs to mature independently of forking schedule. When mature, they can be added to the next scheduled fork.

Steps for EIPs:
1. Endorsement (by major clients, developers and community stakeholders)
2. Implementation (merged into major clients)
3. Testing
4. Acceptance (Allocate to a specific hard fork)

# TL;DR

- The London fork follows Berlin.
- Berlin was originally conceptualised as 'the fork containing the EIPs not quite ready for Istanbul'. 
- EIPs proposed during the coordination for Istanbul and Berlin are valid, but may not get attention during the lead up to those forks.
- Smaller frequent forks are preferred, so EIPs that are desired and ready can be flagged here for awareness.
- EIPs can be created, disseminated, discussed and polished independently so that when London planning is on the agenda, EIPs can be ready for serious consideration.

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
|9|TBD|TBD|Berlin|
|10|TBD|TBD|**London**|
|11|TBC|TBC|Shanghai|
|12|TBC|TBC|Devcon names thereafter|


# Timeline
Details to follow after Berlin fork is completed

# Proposals

Meta-EIP will be created following the Berlin fork.

### Starting list

The following EIPs have been loosely referenced for inclusion in a fork, and may be proposed by the EIP author at some point for inclusion in the London fork.
- First stage of state rent EIPs
- **EIP suggestions welcome here**

### Selection process

Review of the EIPs will be ongoing, those complete the following hurdles will progress
1. Endorsement (Community sentiment, developer agreement)
2. Implementation (merged into major clients)
3. Testing (Including final checks from the testing team)
4. Acceptance (Confirmation that the EIP will specifically go in the Berlin fork)


# Post-London

The next fork will be called Shanghai, in keeping with the DevCon location sequence. 

The fork will consist of EIPs mature enough to go in, following the EIP-centric development cycle. Forks will preferentially be small and on-time rather than large and late, with the knowledge that regular forks allow almost-ready EIPs a concrete timeline for incorporation.