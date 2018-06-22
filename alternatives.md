<!-- TITLE: Alternatives -->
<!-- SUBTITLE: Subtitle for Alternatives -->

# This is the H1 header, not the title


### Randomness



Context: full PoS with Casper CBC and sharding will require a verifiable randomness function that is secure and decentralized, in order to randomly select and assign validators, shuffle notaries, and select collation/block proposers. Such a VRF is an ongoing topic of research, and is yet to be specified and implemented. 



* [Sharding Fork Choice rule PoC with RANDAO and more info, 2018 May 1](https://twitter.com/VitalikButerin/status/991021062811930624)

* [Vitalik's blog post on Randomness with RANDAO preferred](https://vitalik.ca/files/randomness.html)

* [RANDAO++](https://twitter.com/VitalikButerin/status/734735362493427713) plus [an implementation of it with RNGesus](https://github.com/zweicoder/RNGesus)

* A random beacon [as used by Dfinity]() although note that BLS is prone to 51% attacks while RANDAO++ isn't.

* [James' tweet thread analysing Dfinity's BLS randomness beacon in comparison to RANDAO](https://twitter.com/JamesCRay01/status/984289250400075777).

* ethresear.ch post: [PoSW random beacon](https://ethresear.ch/t/posw-random-beacon/1814). [Here](https://gitter.im/ethereum/sharding?at=5adf53096d7e07082b2bdf44) is a critique by Vitalik on Gitter.

* the blockhash, generated via PoW, e.g. [Ethash](https://ethereum.github.io/yellowpaper/paper.pdf#appendix.J). You could use the blockhash as a preimage to hash functions e.g. in RANDAO.

* https://ethresear.ch/t/rng-exploitability-analysis-assuming-pure-randao-based-main-chain/1825

* [RANDAO exploitability analysis results](https://gitter.im/ethereum/sharding?at=5af228fc40f24c43046242f9)



### Alternative blockchain/consensus protocol projects



Alternative approaches to scaling other than sharding include state channels, side chains, multi-chains and off-chain computation. Projects are included [here in this summary spreadsheet by the Web3 Foundation](https://docs.google.com/spreadsheets/d/1BQ0bK_LhSQvxtvXryVoIcmxeKMuVJCq6oD0aS5_hpC8). [Parity Substrate](https://www.reddit.com/r/ethereum/comments/8dgoup/parity_substrate/) is another project. Other designs and sources of inspiration include:

- [Dfinity](https://www.dfinity.org/pdf-viewer/pdfs/viewer?file=../library/dfinity-consensus.pdf), uses a random beacon chain and notaries, which Ethereum plans to implement, although the randomness source may be [RANDAO](https://github.com/ethereum/research/blob/master/sharding_fork_choice_poc/beacon_chain_node.py) instead of BLS aggregate signatures.

- [Truebit](https://truebit.io/) interactive verification off-chain protocol for Ethereum.



Potential sources of inspiration / other projects include:

- [PHANTOM and SPECTRE, alternative DAG designs](https://ethresear.ch/t/phantom-and-spectre-by-a-zohar-and-y-sompolinsky/1888)

- [Ziliqa](https://docs.zilliqa.com/whitepaper.pdf): a PoW sharded architecture consisting of a dataflow smart contract layer, and 5 other layers. Uses the EC-Schnorr multiginature signature scheme. However, RANDAO is preferable to aggregate/multisignature schemes since it is not prone to a 51% attack. Also uses committees, as is planned with Dfinity and Ethereum, although here the committees manage how miners are assigned to shards, whereas in Ethereum that is the task of the beacon chain and the sharding manager contract on the main chain. Uses PBFT consensus, which doesn't seem to be as good as [Casper](http://wikijs.ethereum.wiki/Casper-Proof-of-Stake-compendium) [FFG](https://eips.ethereum.org/EIPS/eip-1011), which is also used with PoW.

- [Cardano](https://cardanodocs.com/introduction/)

- [Algorand](https://www.algorand.com/whitepapers/)

- [OmniLedger](https://eprint.iacr.org/2017/406.pdf)

- [Snowflake to Avalanche: A Novel Metastable Consensus Protocol Family for

Cryptocurrencies](https://ipfs.io/ipfs/QmUy4jh5mGNZvLkjies1RWM4YuvJh5o2FYopNPVYwrRVGV): it's a probabilistic consensus protocol that is synchronous on paper, but has been developed on a real internet (which is partially synchronous).

- [RChain](http://architecture-docs.readthedocs.io/introduction/motivation.html): aims to support scalable, mission-critical projects, without enforcing a strict total order on all transactions in the blockchain (which poses problems around consensus, double-spending, etc.)

- [EOS](https://eos.io/): experienced a liveness fault and locked accounts to prevent theft just days after launch (which has spillover effects to other cryptocurrencies if exchanges decide to socialize losses from EOS, e.g. by freezing accounts of EOS and other cryptocurrencies and declaring bankruptcy, which in turn has legal implications), is controlled by a relatively centralised server and cartel of 21 block producers, does not have a provably correct-by-construction, formally verified consensus protocol,  is very expensive with deposits instead of fees (deploying Cryptokitties on it at it's peak would cost about $1.5b in staked deposits). Sources e.g. [1](https://www.coindesk.com/cold-reception-crypto-reacted-eos-blockchain-freeze/), [2](https://www.coindesk.com/eos-locked-7-accounts-implications-everyone-crypto/). [3](https://ethresear.ch/t/against-replacing-transaction-fees-with-deposits/940/3), [4](https://ethresear.ch/t/against-replacing-transaction-fees-with-deposits/940?u=jamesray1)

- plus a lot more inspiration from research literature.



### Economics



* https://vitalik.ca/
