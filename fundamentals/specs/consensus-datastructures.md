# Consensus Datastructures

```text
Block =
	ParentHash: BlockHash
	UncleHash: BlockHash[]
	MinerAddress: Address
	StateRoot: StateRoot
	TransactionRoot: TransactionRoot
	TransactionReceiptRoot: TransactionReceiptRoot
	LogsBloom: Bytes256
	Difficulty: UInt256
	Number: UInt256
	GasLimit: UInt64
	GasUsed: UInt64
	Timestamp: UInt256
	ExtraData: UInt256
	ProofOfWork: Bytes32 // AKA: MixHash; AKA: MixDigest
	Nonce: Bytes8
```

```text
BlockHash = keccak256(rlp(Block))
```

```text
StateRoot = patriciaTrie(keccak256(Address) => rlp(Account)).rootHash
```

```text
StorageRoot = patriciaTrie(keccak256(StorageSlot: UInt256) => Bytes32).rootHash
```

```text
TransactionRoot = patriciaTrie(rlp(TransactionIndexInBlock) => rlp(Transaction)).rootHash
```

```text
TransactionReceiptRoot = patriciaTrie(rlp(TransactionIndexInBlock) => rlp(TransactionReceipt)).rootHash
```

```text
Account =
	Nonce: UInt64
	Balance: UInt256
	StorageRoot: Bytes32
	CodeHash: Bytes32
```

```text
Transaction =
	AccountNonce: UInt64
	Price: UInt256
	GasLimit: UInt64
	Amount: UInt256
	Payload: Bytes
	V: UInt256
	R: UInt256
	S: UInt256
```

```text
TransactionReceipt =
	CumulativeGasUsed: UInt64
	LogsBloom: Bytes256
	Logs: Log[]
	PostStateOrStatus: UInt32
```

```text
Log =
	LoggerAddress: Address
	LogTopics: Bytes32[]
	LogData: Bytes
```
