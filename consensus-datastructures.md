<!-- TITLE: Consensus Datastructures -->

```
Block =
	ParentHash: BlockHash,
	UncleHash: BlockHash[],
	MinerAddress: Address,
	StateRoot: StateRoot,
	TransactionRoot: TransactionRoot,
	TransactionReceiptRoot: TransactionReceiptRoot,
	LogsBloom: BloomFilter,
	Difficulty: UInt256,
	Number: UInt256,
	GasLimit: UInt64,
	GasUsed: UInt64,
	Timestamp: UInt256,
	ExtraData: UInt8[32],
	ProofOfWork: Keccak256, // AKA: MixHash; AKA: MixDigest
	Nonce: UInt8[8],
```

```
BlockHash = keccak256(rlp(Block))
```

```
StateRoot = patriciaTree(keccak256(Address) => rlp(
	Nonce,
	Balance,
	StorageRoot,
	CodeHash,
))
```

```
StorageRoot = patriciaTree(UInt256 => UInt256)
```

```
TransactionRoot = patriciaTree(rlp(TransactionIndexInBlock) => rlp(Transaction)).rootHash
```

```
TransactionReceiptRoot = patriciaTree(rlp(TransactionIndexInBlock) => rlp(TransactionReceipt)).rootHash
```

```
Transaction =
	AccountNonce: UInt64
	Price: UInt256
	GasLimit: UInt64
	Amount: UInt256
	Payload: UInt8[]
	V: UInt256
	R: UInt256
	S: UInt256
```

```
TransactionReceipt =
	PostStateOrStatus: StateRoot|UInt32, // TODO: figure out what this union actually means
	CumulativeGasUsed: UInt64,
	LogsBloom: BloomFilter,
	Logs: Log[],
```
