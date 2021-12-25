<!-- TITLE: Maintainers -->
<!-- SUBTITLE: List of specifications and maintainers of the Ethereum network, sub protocols, and related standards -->

The [wiki home page](/) has links to some of these items. The purpose of this page is to list out the specifications, where they are maintained, and who the maintainers responsible are.

| Component | Specification	| Maintainers | Notes |
|---|---|---|---|
| Ethereum Virtual Machine (EVM) - specification for processing smart contract code at the core of Ethereum | [Yellow Paper ethereum/yellowpaper](https://github.com/ethereum/yellowpaper) & [JelloPaper](https://jellopaper.org)[^jellopaper] | [nicksavers](https://github.com/nicksavers)[^yellowpapermaintainer] | See local wiki page [EVM Awesome List](/concepts/evm/ethereum-virtual-machine-(evm)-awesome-list.md) for additional resources |
| DevP2P - peer-to-peer networking protocols used by Ethereum | [ethereum/devp2p](https://github.com/ethereum/devp2p/) | [subtly](https://github.com/subtly), [Felix Lange](https://github.com/fjl) |
| JSON-RPC API - middleware interface used to talk to Ethereum nodes | [ethereum/wiki](/json-rpc/api.md) | [bitpshr](https://github.com/bitpshr) (proposed) | See footnote [^jsonrpc] |
| Contract ABIs | [solidity docs](https://solidity.readthedocs.io/en/develop/abi-spec.html)| UNKNOWN | See local wiki page [/archive/ethereum-contract-abi.md](/archive/ethereum-contract-abi.md) |
| Interfaces Repo | [ethereum/interfaces](https://github.com/ethereum/interfaces) | UNKNOWN | |
| Light Ethereum Subprotocol (LES) - protocol to support light nodes of mobile, embedded, and other low resource clients | [zsfelfoldi/go-ethereum/wiki](https://github.com/zsfelfoldi/go-ethereum/wiki/Light-Ethereum-Subprotocol-%28LES%29) | [zsfelfoldi](https://github.com/zsfelfoldi) | See the local wiki page [Light-client-protocol](/concepts/light-client-protocol.md) for more info |
| Whisper - a communication protocol for DApps to communicate with each other | [go-ethereum/wiki Whisper v6 RPC API](https://github.com/ethereum/go-ethereum/wiki/Whisper-v6-RPC-API)  | UNKNOWN | Local wiki pages [Whisper](/concepts/whisper/whisper.md) & [Whisper Overview](/concepts/whisper/overview.md) are from go-ethereum/wiki |
| Swarm | [go-ethereum/2959](https://github.com/ethereum/go-ethereum/pull/2959) | UNKNOWN | See local wiki page [Swarm Hash](/concepts/swarm-hash.md) & [original 2015 info on go-ethereum/wiki](https://github.com/ethereum/go-ethereum/wiki/Swarm---distributed-preimage-archive) & maybe [ethereum/wiki/Distributed-Preimage-Archive](/ideas/distributed-preimage-archive.md) |

[^jsonrpc]: The JSON-RPC spec is stale / unmaintained. [EIP-1474 has been merged as draft](http://eips.ethereum.org/EIPS/eip-1474), and some work to have a separate spec repo here [ethereum-json-rpc-spec](https://github.com/spadebuilders/ethereum-json-rpc-spec). [bitpshr](https://github.com/bitpshr) has volunteered to be a maintainer.

[^yellowpapermaintainer]: See [issue #725 in the ethereum/yellowpaper repo](https://github.com/ethereum/yellowpaper/issues/725)

[^jellopaper]: The [Jello Paper](https://jellopaper.org) is "is an attempt at defining the EVM semantics using the [KEVM project](https://github.com/kframework/evm-semantics)". There is an [EthMagicians discussions about making the Jello Paper the canonical version](https://ethereum-magicians.org/t/jello-paper-as-canonical-evm-spec/2389).

