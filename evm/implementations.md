<!-- TITLE: Ethereum Virtual Machine (EVM) Implementations -->
<!-- SUBTITLE: A list of all the EVM implementations, including private chains -->

All the ETH1 Clients include an EVM implementation, so they are copy-pasted from the [source page](/eth1/clients) for convenience.

|Client Name|Organization|Programming Language|License|
|---|---|---|---|
|[Geth](https://github.com/ethereum/go-ethereum)|Ethereum Foundation|Go|GPLv3|
|[Parity Ethereum](https://github.com/paritytech/parity-ethereum)|Parity|Rust|GPLv3|
|[Aleth](https://github.com/ethereum/aleth)|Ethereum Foundation|C++|GPLv3|
|[EthereumJ + Harmony](https://github.com/ethereum/ethereumj)|Ethereum Foundation / EtherCamp|Java|L/GPLv3|
|[Trinity](https://trinity.ethereum.org/)|Ethereum Foundation|Python|MIT|
|[EthereumJS](https://ethereumjs.github.io/)|EthereumJS|JavaScript|MPL 2.0|
|[Mana](https://github.com/mana-ethereum/mana)|POA Network|Elixir|Apache 2.0 / MIT|
|[Nethermind](https://github.com/tkstanczak/nethermind)|Nethermind|C# / .NET Core|MIT|
|[Hyperledger Besu](https://github.com/hyperledger/besu/)|PegaSys|Java|Apache 2.0|

## Additional Clients & Standalone EVM Implementations

Some of these are full clients to connect to alternate and/or private Ethereum-based chains, others are just EVM implementations meant to run smart contracts.

|Client Name|Organization|Programming Language|License|Notes|
|---|---|---|---|---|
|[SputnikVM](https://github.com/ETCDEVTeam/sputnikvm)|ETCDEV|Rust|Apache 2.0|Standalone Rust implementation of EVM meant to be plugged into different chains|
|[Mantis](https://github.com/input-output-hk/mantis/)|IOHK|Scala|Apache 2.0|Client for Ethereum Classic|
|[Classic Geth](https://github.com/ethereumproject/go-ethereum)|ETCDEV|Go|LGPL 3.0|Ethereum Classic fork of Geth|
|[Hyperledger Burrow](https://github.com/hyperledger/burrow)|Hyperledger|Go|Apache 2.0||
|[Enclave ready EVM - eEVM](https://github.com/microsoft/eevm)|Microsoft|C++|MIT|Designed to be used with Trusted Computing eg. SGX enclaves; no gas counting implemented|

### Discussions

* @bmann is researching how EVM implementations track compatibility -- do they have their own specs? Do they point at the EIPs repo? Refer to Yellow Paper? [Please join the discussion on EthMagicians](https://ethereum-magicians.org)
