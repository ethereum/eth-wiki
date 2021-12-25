---
title: json-rpc
description: 
published: true
date: 2020-06-11T09:38:51.268Z
tags: 
---

# JSON RPC API

[JSON](http://json.org/) is a lightweight data-interchange format. It can represent numbers, strings, ordered sequences of values, and collections of name/value pairs.

[JSON-RPC](http://www.jsonrpc.org/specification) is a stateless, light-weight remote procedure call (RPC) protocol. Primarily this specification defines several data structures and the rules around their processing. It is transport agnostic in that the concepts can be used within the same process, over sockets, over HTTP, or in many various message passing environments. It uses JSON ([RFC 4627](http://www.ietf.org/rfc/rfc4627.txt)) as data format.

Geth has pub/sub support since version 1.4. See [this](https://github.com/ethereum/go-ethereum/wiki/RPC-PUB-SUB) page for more information.

OpenEthereum (f.k.a. Parity) experimental pub/sub support since version 1.6. See [this](https://openethereum.github.io/JSONRPC-parity_pubsub-module.html) for more information.

Hyperledger Besu has pub/sub support since version 1.3. See [this](https://besu.hyperledger.org/en/stable/HowTo/Interact/APIs/RPC-PubSub/) for more information.

Nethermind has pub/sub support. See [this](https://docs.nethermind.io/nethermind/ethereum-client/json-rpc/subscribe) for more information.

## JavaScript API

To talk to an ethereum node from inside a JavaScript application use the [web3.js](https://github.com/ethereum/web3.js) library, which gives a convenient interface for the RPC methods.

See the [JavaScript API](/archive/javascript-api.md) for more details.

## JSON-RPC Endpoint

Default JSON-RPC endpoints:

| Client | URL |
|-------|:------------:|
| C++ |  http://localhost:8545 |
| Go |http://localhost:8545 |
| Py | http://localhost:4000 |
| Parity | http://localhost:8545 |
| Hyperledger Besu | http://localhost:8545 |

### Go

You can start the HTTP JSON-RPC with the `--rpc` flag:

```bash
geth --rpc
```

change the default port (8545) and listing address (localhost) with:

```bash
geth --rpc --rpcaddr <ip> --rpcport <portnumber>
```

If accessing the RPC from a browser, CORS will need to be enabled with the appropriate domain set. Otherwise, JavaScript calls are limit by the same-origin policy and requests will fail:

```bash
geth --rpc --rpccorsdomain "http://localhost:3000"
```

The JSON RPC can also be started from the [geth console](https://github.com/ethereum/go-ethereum/wiki/JavaScript-Console) using the `admin.startRPC(addr, port)` command.


### C++

You can start it by running `eth` application with `-j` option:
```bash
./eth -j
```

You can also specify JSON-RPC port (default is 8545):
```bash
./eth -j --json-rpc-port 8079
```

### Python
In python the JSONRPC server is currently started by default and listens on `127.0.0.1:4000`

You can change the port and listen address by giving a config option.

`pyethapp -c jsonrpc.listen_port=4002 -c jsonrpc.listen_host=127.0.0.2 run`

### Java

Run a Besu node on mainnet with the HTTP JSON-RPC service enabled:

```bash
besu --rpc-http-enabled
```
More details can be found in the [documentation](https://besu.hyperledger.org/en/stable/Reference/CLI/CLI-Syntax/#rpc-http-enabled).

## JSON-RPC support

| | go-ethereum | py-ethereum| open-ethereum | hyperledger-besu |
|-------|:------------:|:-----------:|:-----------:|:-----:|:-----:|
| JSON-RPC 1.0 |  | | | |
| JSON-RPC 2.0 |  &#x2713; | &#x2713; | &#x2713; | &#x2713; |
| Batch requests |  &#x2713; |  &#x2713; | &#x2713; | &#x2713; |
| HTTP |  &#x2713; | &#x2713; | &#x2713; | &#x2713; |
| IPC |  &#x2713; | | &#x2713; | |
| WS | |  | &#x2713; | &#x2713; |

## HEX value encoding

At present there are two key datatypes that are passed over JSON: unformatted byte arrays and quantities. Both are passed with a hex encoding, however with different requirements to formatting:

When encoding **QUANTITIES** (integers, numbers): encode as hex, prefix with "0x", the most compact representation (slight exception: zero should be represented as "0x0"). Examples:
- 0x41 (65 in decimal)
- 0x400 (1024 in decimal)
- WRONG: 0x (should always have at least one digit - zero is "0x0")
- WRONG: 0x0400 (no leading zeroes allowed)
- WRONG: ff (must be prefixed 0x)

When encoding **UNFORMATTED DATA** (byte arrays, account addresses, hashes, bytecode arrays): encode as hex, prefix with "0x", two hex digits per byte. Examples:
- 0x41 (size 1, "A")
- 0x004200 (size 3, "\0B\0")
- 0x (size 0, "")
- WRONG: 0xf0f0f (must be even number of digits)
- WRONG: 004200 (must be prefixed 0x)

Currently [cpp-ethereum](https://github.com/ethereum/cpp-ethereum),[go-ethereum](https://github.com/ethereum/go-ethereum), and [parity](https://github.com/paritytech/parity) provide JSON-RPC communication over http and IPC (unix socket Linux and OSX/named pipes on Windows). Version 1.4 of go-ethereum, version 1.6 of Parity and version 1.3 of Hyperledger Besu onwards have websocket support.

## The default block parameter

The following methods have an extra default block parameter:

- [eth_getBalance](https://openethereum.github.io/JSONRPC-eth-module#eth_getbalance)
- [eth_getCode](https://openethereum.github.io/JSONRPC-eth-module#eth_getcode)
- [eth_getTransactionCount](https://openethereum.github.io/JSONRPC-eth-module#eth_gettransactioncount)
- [eth_getStorageAt](https://openethereum.github.io/JSONRPC-eth-module#eth_getstorageat)
- [eth_call](https://openethereum.github.io/JSONRPC-eth-module#eth_call)

When requests are made that act on the state of ethereum, the last default block parameter determines the height of the block.

The following options are possible for the defaultBlock parameter:

- `HEX String` - an integer block number
- `String "earliest"` for the earliest/genesis block
- `String "latest"` - for the latest mined block
- `String "pending"` - for the pending state/transactions

## Curl Examples Explained

The curl options might return a response where the node complains about the content type, this is because the --data option sets the content type to application/x-www-form-urlencoded . If your node does complain, manually set the header by placing -H "Content-Type: application/json" at the start of the call.

The examples also do not include the URL/IP & port combination which must be the last argument given to curl e.x. 127.0.0.1:8545

## JSON-RPC methods

The full list of JSON-RPC methods is now maintained in the [eth1.0-apis repository](https://github.com/ethereum/eth1.0-apis).