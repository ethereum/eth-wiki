<!-- TITLE: Clients, tools, dapp browsers, wallets and other projects -->



## Ethereum Clients

Ethereum clients run the [Ethereum Virtual Machine](Ethereum-Virtual-Machine-(EVM)-Awesome-List) and are written in a programming language. Clients include:
- Geth (Go) [wiki](https://github.com/ethereum/go-ethereum/wiki), [repo](https://github.com/ethereum/go-ethereum), [issues](https://github.com/ethereum/go-ethereum/issues), (fully working, i.e. passing all JSON tests for the VM, plus can run a full node)
- Parity (Rust) [wiki](https://wiki.parity.io), [repo](https://github.com/paritytech/parity) (fully working)
- cpp-ethereum (C++) [docs](http://www.ethdocs.org/en/latest/ethereum-clients/cpp-ethereum/), [repo](https://github.com/ethereum/cpp-ethereum) (fully working)
- pyethapp (Python) [wiki](https://github.com/ethereum/pyethapp/wiki), used for [Casper FFG](https://github.com/ethereum/research/blob/master/papers/casper-basics/casper_basics.pdf), [repo](https://github.com/ethereum/pyethapp). Includes [py-ethereum](https://github.com/ethereum/pyethereum), which in turn includes [Serenity](https://github.com/ethereum/pyethereum/tree/serenity) R&D.
- [py-evm/Trinity (Python, has a sharding implementation under development)](https://github.com/ethereum/py-evm), a full client (near completion as of late April 2018) developed from Py-ethereum. (almost fully working)
- [ethereumjs-vm repo (Javascript)](https://github.com/ethereumjs/ethereumjs-vm)
- [EWasm](EWasm-compendium), just an alternative to the EVM that is compliant with the EVM ABI.
- [Sharding implementations](Sharding-introduction-R&D-compendium#implementations) for Geth by Prysmatic Labs, Parity by Drops of Diamond, py-evm, Pegasys, and Nimbus.
- [Harmony/ethereumj (Java)](https://github.com/ethereum/ethereumj) (fully working)
- [Exthereum](https://github.com/exthereum/evm) (Elixir) (fully working EVM implementation, not a client).
- [ciri](https://github.com/ciri-ethereum/ciri) (Ruby) (WIP)
- [Solidity](%C3%90App-Development#solidity) [EVM](https://github.com/Ohalo-Ltd/solevm) (Poc), not intended to be a complete client, just for runtime one-off execution.

Plus [more](https://ethereum.stackexchange.com/questions/269/what-exactly-is-an-ethereum-client-and-what-clients-are-there#279).

## Other projects, tools, etc.
- [sharding](Sharding-introduction-R&D-compendium)
- [Casper Proof-of-Stake](Casper-Proof-of-Stake-compendium)
- [smart contract languages](%C3%90App-Development):
   - Solidity: [repo](https://github.com/ethereum/solidity), join the chat at https://gitter.im/ethereum/solidity, [docs](https://solidity.readthedocs.org/en/latest/), see the above link for more resources.
   - Vyper: [repo](https://github.com/ethereum/vyper)
   - LLL and other deprecated languages
- [Mist](https://github.com/ethereum/mist), join the chat at https://gitter.im/ethereum/mist, [issues](https://github.com/ethereum/mist/issues). Note that as of 31 May 2018, Mist isn't really user-ready yet, so until it has a stable release, using alternatives like [MyCrypto](https://www.mycrypto.com/) or [MyEtherWallet](https://www.myetherwallet.com/) is recommended instead, unless you're happy to be a beta tester.
- web3 or JSON.RPC: [repo](https://github.com/ethereum/web3.js), [issues](https://github.com/ethereum/web3.js/issues)
- Organization projects include:
   - https://github.com/ethereum,
   - https://github.com/paritytech, and 
   - https://github.com/ethereumjs.
- Also see other projects in the sidebar of this wiki, e.g. Ethereum technologies, infrastructure, dapp development, etc. or try searching.
