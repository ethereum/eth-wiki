<!-- TITLE: FAQs -->

[![Documentation chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)

> Answers to questions about Ethereum



# Ethereum

## What is Ethereum?

There are several ways to answer this question, such as [here](http://wikijs.ethereum.wiki/Ethereum-introduction), as well as the dedicated [What is Ethereum](http://github.com/ethereum/wiki/wiki/What-is-Ethereum) wiki page, which was made at the time of the Frontier release, so it is outdated.

If you prefer to learn by watching videos, see:
 + [Introducing Ethereum](https://www.youtube.com/watch?v=Clw-qf1sUZg) (Video, 10mi)
 + [Vitalik Buterin reveals Ethereum at Bitcoin Miami 2014](http://youtu.be/l9dpjN3Mwps) (Video, 28min)
 + [Singularity 1 on 1: Ethereum is a Decentralized Consensus Platform](http://youtu.be/fbEtivJIfIU) (Video, 69min)
 + [Our second Reddit "Ask Me Anything" for community selected questions](http://www.reddit.com/r/IAmA/comments/2bjmgb/hi_we_are_the_ethereum_project_team_ask_us/) (not actually a video)

# How do I buy Ether or ETH?

Read [this](http://wikijs.ethereum.wiki/Ethereum-introduction.md#how-do-you-buy-and-sell-ether-the-currency-of-ethereum).

# Where can I learn more about Ethereum?

- Main site: https://www.ethereum.org
- Forums: https://forum.ethereum.org
- Github: https://github.com/ethereum
- Blog: https://blog.ethereum.org
- Wiki: http://ethereum.wiki (this wiki)
- Twitter: https://twitter.com/ethereum
- Meetups: http://ethereum.meetup.com
- Whitepaper: https://github.com/ethereum/wiki/wiki/White-Paper
- Yellow Paper: https://ethereum.github.io/yellowpaper/paper.pdf
- Facebook: https://www.facebook.com/ethereumproject
- Youtube: http://www.youtube.com/ethereumproject
- Google+: http://google.com/+EthereumOrgOfficial
- IRC Freenode: #ethereum (http://bitly.com/IRC_ethereum for weblink)
- Stack Exchange: https://ethereum.stackexchange.com

# Where can I find the main project repositories?
+ [go-ethereum](https://github.com/ethereum/go-ethereum) ([@obscuren](https://github.com/obscuren), [@maran](https://github.com/maran))
+ [Parity](https://github.com/paritytech/parity)
+ [cpp-ethereum](https://github.com/ethereum/cpp-ethereum/) ([@gavofyork](https://github.com/gavofyork), [@programmerTim](https://github.com/programmerTim), [@caktux](https://github.com/caktux))
+ [pyethereum](https://github.com/ethereum/pyethereum) ([@vbuterin](https://github.com/vbuterin), [@heikoheiko](https://github.com/heikoheiko), [@chenhouwu](https://github.com/chenhouwu))
+ [ethereumj](https://github.com/ethereum/ethereumj) ([@romanman](https://github.com/romanman), [@nicksavers](https://github.com/nicksavers))
+ [ethereumjs-lib](https://github.com/ethereum/ethereumjs-lib) ([@ethers](https://github.com/ethers), [@wanderer](https://github.com/wanderer))
+ more repositories are in the [Ethereum organisation on Github](https://github.com/ethereum)

# Where can I learn about the Ether sale and mining?

+ [The Ether Sale FAQ](https://forum.ethereum.org/discussion/196/the-ether-sale-faq/p1)
+ [The Mining FAQ](https://forum.ethereum.org/discussion/197/mining-faq-live-updates/p1)

# Wallets

If you have an issue with your wallet, an exchange or other matters relating to using the Ether cryptocurrency or making transactions, see this [MyEtherWallet knowledge base](https://myetherwallet.github.io/knowledge-base/). It answers many FAQs such as:
* [transaction is not showing up or is pending forever](https://myetherwallet.github.io/knowledge-base/transactions/transactions-not-showing-or-pending.html)
* [ETH or Tokens sent to or from exchange haven't shown up / Transaction says complete, but funds haven't shown up yet](https://myetherwallet.github.io/knowledge-base/faq/eth-or-tokens-not-showing-on-exchange.html)
* [Phish, Hacks, Thefts & stolen funds due to phishing messages on Slack / Reddit / Google Ads](https://myetherwallet.github.io/knowledge-base/security/phish-hacks-thefts-and-stolen-funds-due-to-phishing.html)

# Clients

## Where can I find official releases?
Clients:
+ [Releases for Geth](https://github.com/ethereum/go-ethereum/releases) (Go)
+ [Releases for Parity](https://github.com/paritytech/parity/releases) (Rust)
+ [Releases for eth](https://github.com/ethereum/cpp-ethereum/releases) (C++)
+ [Releases for Pyethereum](https://github.com/ethereum/pyethereum/releases) (Python)
+ [Releases for Ethereumj](https://github.com/ethereum/ethereumj/releases) (Java)
+ [Releases for EthereumJS](https://github.com/ethereumjs) (Javascript)

Other:
+ [Releases for Mist](https://github.com/ethereum/go-ethereum/releases) (wallet and browser for dapps)
+ [Releases for Pyethapp](https://github.com/ethereum/pyethapp/releases) (Python)
+ [Releases for Py-EVM](https://github.com/ethereum/py-evm/releases) (Python)


## How to install development builds?

+ Homebrew
  + [Homebrew Ethereum](https://github.com/caktux/homebrew-ethereum) ([@caktux](https://github.com/caktux))
+ Guides
  + [eth/AlethZero super easy install guide for OSX](https://forum.ethereum.org/discussion/1388/alethzero-super-easy-install-guide-for-osx) ([@stephantual](https://github.com/stephantual))
  + [Go-Ethereum simple build guide for OSX](http://forum.ethereum.org/discussion/905/go-ethereum-cli-ethereal-simple-build-guide-for-osx-now-with-one-line-install) ([@stephantual](https://github.com/stephantual))
  + [Building on Ubuntu](https://github.com/ethereum/cpp-ethereum/wiki/Building-on-Ubuntu#user-content-trusty-1404)
+ Builds
  + [Ethdev Buildbot](http://build.ethdev.com/waterfall)

## How to install the clients from source?

+ [Building eth/AlethZero (C++)](https://github.com/ethereum/cpp-ethereum#building-from-source)
+ [Building Mist (Go)](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum%28Go%29)
+ [Installing Pyethereum (Python)](https://github.com/ethereum/pyethereum#quickstart)
+ [Installing EthereumJ (Java)](https://github.com/ethereum/ethereumj#maven)
+ [Installing Ethereumjs-lib (JavaScript for Browser and Node)](https://github.com/ethereum/ethereumjs-lib#install)

## Mining

### How can I mine Ether?

With eth/AlethZero

+ To process transactions
  + Disable "Debug" > "Force Mining"
  + Click "Mine"
+ To force mine (Use sparingly, unless stress testing)
  + Enable "Debug" > "Force Mining"
  + Click "Mine"

With the eth client

```
# Only force mine to acquire ether or stress test
$ eth --force-mining --mining on [YOUR OPTIONS...]
```

# Contracts

## Where can I learn about contract development?

+ Articles
  + [Ethereum Development Tutorial](http://wikijs.ethereum.wiki/Ethereum-Development-Tutorial)
+ Videos
  + [Ethereum](https://www.youtube.com/user/ethereumproject/videos)
  + [EtherCasts](https://www.youtube.com/user/EtherCasts/videos)

## Where can I learn Serpent, the Python-like language?

+ Specifications
  + [The Serpent Language](http://wikijs.ethereum.wiki/Serpent)
+ Examples
  + [Vitalik's Serpent examples](https://github.com/ethereum/serpent/tree/master/examples)
+ Tutorials
  + [Pyethereum and Serpent Programming Guide](https://blog.ethereum.org/2014/04/10/pyethereum-and-serpent-programming-guide/)
+ Videos
  + [Learn Ethereum with Vitalik](https://www.youtube.com/watch?v=nXYDfLCLmMs)

## Where can I learn LLL, the Lisp-like language?

+ Specifications
  + [The LLL Language](https://github.com/ethereum/cpp-ethereum/wiki/LLL-PoC-6/7a575cf91c4572734a83f95e970e9e7ed64849ce)
+ Examples
  + [LLL examples for PoC 5](https://github.com/ethereum/cpp-ethereum/wiki/LLL-Examples-for-PoC-5/7a575cf91c4572734a83f95e970e9e7ed64849ce)
+ Videos
  + [Programming Society with Asm](https://www.youtube.com/watch?v=xO1AxsYAkU8)

## Where can I learn Solidity, the JavaScript-like language?

+ Documentation
  + [Solidity Documentation](http://solidity.readthedocs.io/en/latest/index.html)

+ Tutorials
  + [Contract Writing in Solidity](https://dappsforbeginners.wordpress.com)

## How to test contracts?

+ [EVM Contract Simulator](https://github.com/EtherCasts/evm-sim/) ([@EtherCasts](https://github.com/EtherCasts))
+ [Pyethereum Tester](https://github.com/ethereum/pyethereum/blob/master/ethereum/tests/test_contracts.py) ([@ethereum](https://github.com/ethereum))

## Where to find example contracts?

+ Serpent
  + [By Vitalik Buterin](https://github.com/ethereum/serpent/tree/master/examples) ([@vbuterin](https://github.com/vbuterin))
  + [By EtherCasts](https://github.com/EtherCasts) ([@EtherCasts](https://github.com/EtherCasts))
  + [By Rob Myers](https://github.com/robmyers/artworld-ethereum) ([@robmyers](https://github.com/robmyers))
  + [By Tyler Florez](https://github.com/qualiabyte/ethereum-contracts) ([@qualiabyte](https://github.com/qualiabyte))
+ LLL
  + [By Gavin Wood](https://github.com/ethereum/cpp-ethereum/wiki/LLL-Examples-for-PoC-5/7a575cf91c4572734a83f95e970e9e7ed64849ce) ([@gavofyork](https://github.com/gavofyork))
  + [By Dennis Mckinnon](https://github.com/dennismckinnon/Ethereum-Contracts) ([@dennismckinnon](https://github.com/dennismckinnon))
  + [By Doug A.](https://github.com/d11e9/g3) ([@dlle9](https://github.com/d11e9))

# ÐApps

## Where can I learn about the Ethereum APIs?

+ [The PoC 6 API for C++](https://github.com/ethereum/cpp-ethereum/wiki/Client-Development-with-PoC-6)
+ [The PoC 5 API for Go](https://github.com/ethereum/go-ethereum/wiki/PoC-5-Public-Go-API)
+ [The PoC 6 API for QML](https://github.com/ethereum/go-ethereum/wiki/QML-PoC6-API)
+ [The PoC 7 API for JavaScript](http://wikijs.ethereum.wiki/JavaScript-API)

## Where can I learn about ÐApp development?

+ [Writing Your Own Currency](http://hidskes.com/blog/2014/05/21/ethereum-dapp-development-for-web-developers/) ([@maran](https://github.com/maran))

## Where can I find ÐApp development tools?

Official

+ [eth/AlethZero GUI client (C++)](https://github.com/ethereum/cpp-ethereum/wiki/Using-AlethZero)
+ [Eth command-line client (C++)](https://github.com/ethereum/cpp-ethereum/wiki/Using-Ethereum-CLI-Client)
+ [LLLC Compiler (C++)](https://github.com/ethereum/cpp-ethereum/blob/develop/lllc/main.cpp)
+ [Ethereum command-line client (Go)](https://github.com/ethereum/go-ethereum/wiki/Command-Line-Options)
+ [Mist Browser (Go)](https://github.com/ethereum/go-ethereum)
+ [Pyeth command-line client (Python)](https://github.com/ethereum/pyethereum#interacting-with-the-network)
+ [Serpent Compiler (Python)](http://wikijs.ethereum.wiki/Serpent)

Community

+ [Emacs LLL Mode](https://github.com/robmyers/lll-mode) ([@robmyers](https://github.com/robmyers))
+ [Emacs Serpent Mode](https://github.com/robmyers/serpent-mode) ([@robmyers](https://github.com/robmyers))
+ [EVM-Sim](https://github.com/EtherCasts/evm-sim/) ([@EtherCasts](https://github.com/EtherCasts))
+ [MintChalk](http://www.mintchalk.com/) ([@mintchalk](https://github.com/mintchalk))

## Where can I find example ÐApps?

+ [dapp-bin](https://github.com/ethereum/dapp-bin) ([@ethereum](https://github.com/ethereum))
+ [GavCoin](http://gavwood.com/gavcoin.html) ([@gavofyork](https://github.com/gavofyork))
+ [JeffCoin](https://github.com/obscuren/jeffcoin) ([@obscuren](https://github.com/obscuren))
+ [Make It Rain](https://github.com/EtherCasts/make-it-rain) ([@EtherCasts](https://github.com/EtherCasts))
+ [Chronos](https://github.com/mquandalle/chronos) ([@mquandalle](https://github.com/mquandalle))
+ [Artworld-Ethereum](https://github.com/robmyers/artworld-ethereum) ([@robmyers](https://github.com/robmyers))
+ [CryptoCoinWatch](https://github.com/EtherCasts/cryptocoinwatch) ([@EtherCasts](https://github.com/EtherCasts))
+ [Occam's Run](https://github.com/d11e9/Occams-Run) ([@d11e9](https://github.com/d11e9))
+ [TrustDavis](https://github.com/EtherCasts/trustdavis) ([@EtherCasts](https://github.com/EtherCasts))

# IRC

## How can I join the Ethereum IRC channels?

+ [Chat with the ethereum dev community on IRC!](https://forum.ethereum.org/discussion/1495/chat-with-the-ethereum-dev-community-on-irc)

# More Questions and Answers

+ [FAQ by @fivedogit](https://docs.google.com/document/d/14EIe984_86Y-uuNm-a4EsVeD3eI4qAAlz_MZof1qkqM/)