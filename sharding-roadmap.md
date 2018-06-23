<!-- TITLE: Sharding roadmap -->

<h2>Roadmap</h2>

The roadmap is an active area of research. The outline below is only intended to provide flavour. It is intended for this document to be maintained with ongoing R&D.

Sourced originally from the now [retired spec for phase 1 sharding](https://ethresear.ch/t/sharding-phase-1-spec-retired/1407), with modifications.



### <strong>Phase 1</strong>: Basic sharding without EVM
   * Blob shard without transactions
   * Proposers submit blobs
   * Notaries
   * For more details, see [implementations](http://wikijs.ethereum.wiki/Sharding-introduction-R&D-compendium#implementations), e.g. [Drops of Diamond's phase 1 project](https://github.com/Drops-of-Diamond/diamond_drops/projects/1).

### <strong>Phase 2</strong>: EVM state transition function
   * Full nodes only
   * Asynchronous cross-contract calls only
   * [Account abstraction](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-101.md)
   * [eWASM](https://github.com/ewasm/design)
   * Archive accumulators: https://ethresear.ch/t/history-state-and-asynchronous-accumulators-in-the-stateless-model/287 and https://ethresear.ch/t/batching-and-cyclic-partitioning-of-logs/536 and https://ethresear.ch/t/double-batched-merkle-log-accumulator/571
   * Storage rent: [here](https://ethresear.ch/t/a-simple-and-principled-way-to-compute-rent-fees/1455) and [here](https://ethresear.ch/search?q=storage%20rent).
   * [Bandwidth fees](https://ethresear.ch/t/incentivizing-a-robust-p2p-network-relay-layer/1438)

### <strong>Phase 3</strong>: Light client state protocol

   * Executors
   * [State-minimized clients](https://ethresear.ch/t/state-minimised-executions/748). [Stateless clients](https://ethresear.ch/t/the-stateless-client-concept/172) are not ideal as we don't want to offload all storage into secondary markets, rather we can give people a choice to pay storage rent on the blockchain or pay for it in secondary markets.

### <strong>Phase 4</strong>: Cross-shard transactions: see [here](http://notes.ethereum.org/s/BJc_eGVFM#cross-shard-communication) and [more](https://ethresear.ch/search?q=cross-shard).

   * Internally-synchronous zones: [mind map including architectures](https://www.mindomo.com/zh/mindmap/sharding-d7cf8b6dee714d01a77388cb5d9d2a01)
   * See also e.g. https://ethresear.ch/t/synchronous-cross-shard-transactions-with-consolidated-concurrency-control-and-consensus-or-how-i-rediscovered-chain-fibers/2318/5

### <strong>Phase 5</strong>: Tight coupling with main chain security: [here](https://hackmd.io/s/HJ_BbgCFz#%E2%9F%A0-1600---1645--Ethereum-20-End-game) and [more](https://ethresear.ch/search?q=tight%20coupling).

   * Data availability proofs: [A note on data availability and erasure coding](https://github.com/ethereum/research/wiki/A-note-on-data-availability-and-erasure-coding), https://ethresear.ch/t/sharding-and-data-forgetfulness/61, 
   * [Casper](http://wikijs.ethereum.wiki/Casper-Proof-of-Stake-compendium) integration.
   * [Internally fork-free sharding](https://ethresear.ch/search?q=internally%20fork-free)
   * Manager shard

### <strong>Phase 6</strong>: Super-quadratic or exponential sharding

   * Recursively, shards within shards within shards...
   * Load balancing: [Wikipedia](https://en.wikipedia.org/wiki/Load_balancing_(computing)), [search results](https://duckduckgo.com/?q=load+balancing&t=canonical&ia=web). Related: https://ethresear.ch/t/history-state-and-asynchronous-accumulators-in-the-stateless-model/287, https://ethresear.ch/t/state-minimized-implementation-on-current-evm/1255

And a lot more: https://ethresear.ch/c/sharding.

- zk-STARKs, e.g. [StarkWare the startup](https://www.starkware.co/); videos [here](https://www.youtube.com/watch?v=VUN35BC11Qw&t=2s), [here](https://www.youtube.com/watch?v=9VuZvdxFZQo&t=7s) and [here](https://www.youtube.com/watch?v=9VuZvdxFZQo&t=7s), as well as a paper [here](https://eprint.iacr.org/2018/046) (the abstract is a more succinct intro than the videos), while the full paper is more detailed; and 
- [more](https://ethresear.ch/t/are-there-any-ideas-thats-potentially-more-useful-than-implementing-sharding/334/3). 
- [heterogeneous sharding](https://ethresear.ch/t/heterogeneous-sharding/1979)

For more information see https://github.com/ethereum/wiki/wiki/Sharding-introduction-R&D-compendium and https://github.com/ethereum/wiki/wiki/Sharding-FAQs.