<!-- TITLE: Wiki: ethresear.ch Sharding Compendium -->



[Here is everything in the sharding category on https://ethresear.ch](https://ethresear.ch/c/sharding).

### Specifications / proposed protocol architecture:

* https://ethresear.ch/t/per-period-committee-snapshot/1703, particularly [Solution 3 with bitfield counting](https://ethresear.ch/t/per-period-committee-snapshot/1703/9?u=jamesray1)
* https://ethresear.ch/t/a-general-framework-of-overhead-and-finality-time-in-sharding-and-a-proposal/1638
* https://ethresear.ch/t/a-minimal-sharding-protocol-that-may-be-worthwhile-as-a-development-target-now/1650
* Outdated: https://ethresear.ch/t/sharding-phase-1-spec-retired/1407. Critique of the old spec: https://ethresear.ch/t/exploring-the-proposer-collator-split/1632.

### Sub-specifications/proposals

* [Safe notary pool size](https://ethresear.ch/t/safe-notary-pool-size/1728)
* [Expanding on proposer/notary separation](https://ethresear.ch/t/expanding-on-proposer-notary-separation/1691)
* [Blob serialisation](https://ethresear.ch/t/blob-serialisation/1705)
* [Expanding on proposer/notary separation](https://ethresear.ch/t/expanding-on-proposer-notary-separation/1691)

### Interactive verification

Truebit: https://truebit.io/

Ideas that @maxc on ethresear.ch is working on:

> One of the thoughts I've had about Truebit is if the multiple rounds of interactive verification are really necessary. Would just one round suffice If you could just check-point the trace of the execution at multiple steps. 
I was also  wondering if it would  be possible to parallelise verification, if for instance, you used witnesses everytime you read in state to the evm and stored the whole machine state at each check-point rather than just the merkle root.  
An alternative is to break up a transaction into multiple transactions after say a certain number of steps have been read.

### Alternative protocol design and inspiration

* Dfinity: https://dfinity.org/pdf-viewer/pdfs/viewer?file=../library/dfinity-consensus.pdf

### Availability proofs

* https://ethresear.ch/t/simple-honest-majority-collation-availability-proof/1205

### Off-chain schemes for faster finality and other benefits

* https://ethresear.ch/t/off-chain-intermediate-blocks/1680
* https://ethresear.ch/t/offchain-collation-headers/1679

### Ethereum Sharding Research Compendium

http://notes.ethereum.org/s/BJc_eGVFM#

Note that most of the topics in this compendium are concerned with phase 2 and later, or are outdated.

### Improved storage

* https://ethresear.ch/t/data-availability-proof-friendly-state-tree-transitions/1453/6
* https://github.com/ethereum/research/blob/master/trie_research/bintrie2/new_bintrie.py

### A sharding P2P network

* [Torus-shaped sharding network](https://ethresear.ch/t/torus-shaped-sharding-network/1720)

### Phase 2 or later
#### Abstraction
* [A recap of where we are at on account abstraction](https://ethresear.ch/t/a-recap-of-where-we-are-at-on-account-abstraction/1721)

#### Storage
* https://ethresear.ch/t/a-two-layer-account-trie-inside-a-single-layer-trie/210
* https://ethresear.ch/t/detailed-analysis-of-stateless-client-witness-size-and-gains-from-batching-and-multi-state-roots/862

#### Incentivization to externalize internalities and prevent a tragedy of the commons
* https://ethresear.ch/search?q=rent
* https://ethresear.ch/t/incentivizing-a-robust-p2p-network-relay-layer/1438/19
* https://ethresear.ch/t/incentives-for-running-full-ethereum-nodes/1239/35
* https://ethresear.ch/t/incentivizing-full-state-nodes/1640