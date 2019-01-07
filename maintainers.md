<!-- TITLE: Maintainers -->
<!-- SUBTITLE: List of specifications and maintainers of the Ethereum network, sub protocols, and related standards -->

The [wiki home page](/) has links to some of these items. The purpose of this page is to list out the specifications, where they are maintained, and who the maintainers responsible are.

| Component | Specification	| Maintainers | Notes |
|---|---|---|---|
| Ethereum Virtual Machine (EVM) - specification for processing smart contract code at the core of Ethereum | [Yellow Paper ethereum/yellowpaper](https://github.com/ethereum/yellowpaper) | [Nick Savers](https://github.com/nicksavers) | See local wiki page [EVM Awesome List](ethereum-virtual-machine-evm-awesome-list) for additional resources |
| DevP2P - peer-to-peer networking protocols used by Ethereum | [ethereum/devp2p](https://github.com/ethereum/devp2p/) | [subtly](https://github.com/subtly), [Felix Lange](https://github.com/fjl) |
| JSON-RPC API - middleware interface used to talk to Ethereum nodes | [ethereum/wiki](https://github.com/ethereum/wiki/wiki/JSON-RPC) | [bitpshr](https://github.com/bitpshr) (proposed) | See footnote [^jsonrpc] |
| Contract ABIs | [solidity docs](https://solidity.readthedocs.io/en/develop/abi-spec.html)| | See local wiki page [Ethereum-Contract-ABI](Ethereum-Contract-ABI) |
| Interfaces Repo | [ethereum/interfaces](https://github.com/ethereum/interfaces) | | |
| Light Ethereum Subprotocol (LES) - protocol to support light nodes of mobile, embedded, and other low resource clients | [zsfelfoldi/go-ethereum/wiki](https://github.com/zsfelfoldi/go-ethereum/wiki/Light-Ethereum-Subprotocol-%28LES%29) | [zsfelfoldi](https://github.com/zsfelfoldi) | See the local wiki page [Light-client-protocol](Light-client-protocol) for more info |
| Whisper - a communication protocol for DApps to communicate with each other | [go-ethereum/wiki Whisper v6 RPC API](https://github.com/ethereum/go-ethereum/wiki/Whisper-v6-RPC-API)  | | Local wiki pages [Whisper](Whisper) & [Whisper Overview](Whisper-Overview) are from go-ethereum/wiki |
| Swarm | [go-ethereum/2959](https://github.com/ethereum/go-ethereum/pull/2959) | | See local wiki page [Swarm Hash](/glossary/swarm-hash) & [original 2015 info on go-ethereum/wiki](https://github.com/ethereum/go-ethereum/wiki/Swarm---distributed-preimage-archive) & maybe [ethereum/wiki/Distributed-Preimage-Archive](https://github.com/ethereum/wiki/wiki/Distributed-Preimage-Archive) |

[^jsonrpc]: The JSON-RPC spec is stale / unmaintained. There is an [EIP 1474 to have a canonical specification](https://github.com/ethereum/EIPs/pull/1474), and some work to have a separate spec repo here [ethereum-json-rpc-spec](https://github.com/spadebuilders/ethereum-json-rpc-spec). [bitpshr](https://github.com/bitpshr) has volunteered to be a maintainer.

