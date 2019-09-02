---
title: Roadmap
description: Ethereum Roadmap, including links to ETH1x and ETH2 / Serenity
published: true
date: 2019-09-02T11:41:55.190Z
tags: 
---

Prior information is available on the [releases](/releases) page.

The formal process of hardforks is documented in [EIP 233](https://eips.ethereum.org/EIPS/eip-233), along with some recent discussion on [EthMagicians](https://ethereum-magicians.org/t/eep-5-ethereum-hardfork-process-request-for-collaboration/2305).

The [ETH1](/eth1) page lists Working Groups and areas of focus.


# Philosophy

**Pro-fork:** The community has embraced the concept of hard forks, with the understanding that new major changes can be challenging but rewarding.

**Regular cadence:** Forks have increasingly been moving toward a traditional software release-schedule. Regular small hard forks allow upgrades to be included in more timely and manageable way that large infrequent forks, as described [here](https://ethereum-magicians.org/t/more-frequent-smaller-hardforks-vs-less-frequent-larger-ones/2929/28) 

The fork will ideally follow an *EIP-centric* approach outlined [here](https://notes.ethereum.org/@holiman/S1ELAYY7S?type=view). This approach will allow EIPs to mature independently of forking schedule. When mature, they can be added to the next scheduled fork.

Steps for EIPs:
1. Endorsement (by major clients, developers and community stakeholders)
2. Implementation (merged into major clients)
3. Testing
4. Acceptance (Allocate to a specific hard fork)

# Upgrade history

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
|8|TBD|TBD|[Istanbul](/roadmap/istanbul)|
|9|TBD|TBD|[Berlin](/roadmap/berlin)|
|10|TBD|TBD|[London](/roadmap/london)|
|11|TBC|TBC|Shanghai|
|12|TBC|TBC|Devcon names thereafter|

# Frontier

The first block in the Ethereum mainnet.

# Frontier Thawing

Addition of the ice-age to the protocol to make a hard fork *required* in the future. This promoted planned upgrades. More details here [here](https://blog.ethereum.org/2015/08/04/ethereum-protocol-update-1/).

# Homestead

meta-EIP [here](https://eips.ethereum.org/EIPS/eip-606)

# DAO Fork

# Tangerine Whistle 

# Spurious Dragon

# Byzantium

# Constantinople
Initially planned for Q1 of 2019, this fork was delayed to allow for evaluation of one of the EIPs. The fork went ahead without that EIP (EIP-1283) and was referred to by some as the Petersburgh fork. More [here](/roadmap/petersburg).

* [EIP 145](https://eips.ethereum.org/EIPS/eip-145) Bitwise shifting instructions in the EVM
* [EIP 1052](https://eips.ethereum.org/EIPS/eip-1052) EXTCODEHASH opcode
* [EIP 1014](https://eips.ethereum.org/EIPS/eip-1014) Skinny CREATE2
* [EIP 1234](https://eips.ethereum.org/EIPS/eip-1234) Constantinople Difficulty Bomb Delay and Block Reward Adjustment

## Useful Reading
* [Sep 2018 Coindesk article](https://www.coindesk.com/constantinople-ahead-what-you-need-to-know-about-ethereums-big-upgrade)
* [Jan 2019 /u/cartercarlson summary from /r/ethereum](https://www.reddit.com/r/ethereum/comments/abv70c/heres_a_summary_of_the_constantinople_update/)
* [Jan 2019 Ethereum Foundation Blog](https://blog.ethereum.org/2019/01/11/ethereum-constantinople-upgrade-announcement/)

# Istanbul

More details [here](/roadmap/istanbul).

# Berlin

More details [here](/roadmap/berlin).

# London

More details [here](/roadmap/london).

# Subsequent forks

Named after the devcon location sequence
Upgrades will include features that:
- Improve and maintain the mainnet ('ETH1')
- Integrate the mainnet with the scaling upgrade ('Serenity/ETH2'). 
	- Mainnet to recognise the Beacon Chain (phase 0)
  - Mainnet to inherit the finality of the Beacon Chain
  - Mainnet to be added as one shard under the scope of the Beacon Chain
  - Addition of more shards, with interoperability between shards

# Serenity / ETH2
See the [ETH2 Specs Github Repo](https://github.com/ethereum/eth2.0-specs).

The [ETH2 Project Management repo](https://github.com/ethereum/eth2.0-pm) holds ongoing notes and meetings.
