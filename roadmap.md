<!-- TITLE: Roadmap -->
<!-- SUBTITLE: Ethereum Roadmap, including links to ETH 1.x and ETH2 / Serenity -->

Prior information is available on the [releases](/releases) page.

The formal process of hardforks is documented in [EIP 233](https://eips.ethereum.org/EIPS/eip-233), along with some recent discussion on [EthMagicians](https://ethereum-magicians.org/t/eep-5-ethereum-hardfork-process-request-for-collaboration/2305).

# Constantinople
Constantinople is planned for Q1 of 2019. Planned date is January 16th, 2019, 12:00pm UTC.

* [EIP 145](https://eips.ethereum.org/EIPS/eip-145) Bitwise shifting instructions in the EVM
* [EIP 1052](https://eips.ethereum.org/EIPS/eip-1052) EXTCODEHASH opcode
* [EIP 1283](https://eips.ethereum.org/EIPS/eip-1283) Net gas metering for SSTORE without dirty maps
* [EIP 1014](https://eips.ethereum.org/EIPS/eip-1014) Skinny CREATE2
* [EIP 1234](https://eips.ethereum.org/EIPS/eip-1234) Constantinople Difficulty Bomb Delay and Block Reward Adjustment

_Note: listed Github threads for items that are still listed as Draft_

## Useful Reading
* [Sep 2018 Coindesk article](https://www.coindesk.com/constantinople-ahead-what-you-need-to-know-about-ethereums-big-upgrade)
* [Jan 2019 /u/cartercarlson summary from /r/ethereum](https://www.reddit.com/r/ethereum/comments/abv70c/heres_a_summary_of_the_constantinople_update/)
* [Jan 2019 Ethereum Foundation Blog](https://blog.ethereum.org/2019/01/11/ethereum-constantinople-upgrade-announcement/)

# Istanbul
Istanbul is planned for Q4 of 2019. Planned date is October 16th, 2019, 12:00pm UTC.

More details on the [road to Istanbul](/roadmap/istanbul).

_Note: proposals are not discussed yet._
# ETH 1.x
There are a variety of proposals for what is now known as ETH 1.x -- a series of upgrades to add features in support of the full ETH2 specs. These are all at the proposal / discussion stage, without any of them having been turned into EIPs.

The [EthMagicians ETH 1.x Ring](https://ethereum-magicians.org/c/working-groups/ethereum-1-x-ring) has more discussions.

## Storage Rent / Pruning

Problem: on chain storage can't be stored forever. Introduce rent, archiving, pruning, or a variety of other methods to minimize live state storage.

Rent:
https://ethereum-magicians.org/t/ethereum-state-rent-for-eth-1-x-pre-eip-document/2018

Pruning:
https://ethereum-magicians.org/t/ethereum-chain-pruning-for-long-term-1-0-scalability-and-viability/2074

## eWASM
Problem: desire to move to eWASM as the VM.

https://ethereum-magicians.org/t/ewasm-working-group-proposal-for-eth-1-x/2033

## Simulation
Problem: Simulate various parameters of proposed features

https://ethereum-magicians.org/t/simulation-working-group-proposal-for-eth-1-x/2068/2
# Serenity / ETH2
See the [ETH2 Specs Github Repo](https://github.com/ethereum/eth2.0-specs).

The [ETH2 Project Management repo](https://github.com/ethereum/eth2.0-pm) holds ongoing notes and meetings.
