<!-- TITLE: Home -->

# Welcome to the Ethereum Wiki 

Other versions: [Chinese](https://zh.ethereum.wiki) and [Japanese](https://ja.ethereum.wiki).

All of these pages can be edited via the web-interface.  You can also submit Pull Requests at https://github.com/ethresearch/en-ethereum-wiki.  The github and the site are synced every five minutes.


[![Documentation chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)

> Ethereum wiki covering all things related to Ethereum

This is the community maintained wiki covering all sorts of information on the next-generation peer-to-peer technology platform built by the Ethereum Foundation, including **Ethereum**, _the generalized blockchain for smart contract development_, as well as sister protocols like **[Whisper](Whisper-pages)**, _the private low-level datagram communication platform_, and **[Swarm](http://swarm-gateways.net/bzz:/theswarm.eth/)**, a distributed storage platform and content distribution service.


-----

| Basics  	|   R&D	| Infrastructure  	|   	|   	|
|---	|---	|---	|---	|---	|
| [Home](/)  	| [Sharding introduction & R&D Compendium](Sharding-introduction-R&D-compendium), [FAQs](Sharding-FAQs) & [roadmap](Sharding-roadmap)  	|   	|   	|   	|
|  [Ethereum Whitepaper](White-Paper) 	|  [Casper Proof-of-Stake compendium](Casper-Proof-of-Stake-compendium) and [FAQs](Proof-of-Stake-FAQs). 	|   	|   	|   	|
| [Ethereum Introduction](Ethereum-introduction)  	| [Alternative blockchains, randomness, economics, and other research topics](Alternative-blockchains,-randomness,-economics,-and-other-research-topics)  	|   	|   	|   	|
| [Uses: DAOs and dapps](Decentralized-apps-(dapps)) | [Hard Problems of Cryptocurrency](Problems) | | |
| [Getting Ether](Getting-Ether) | [Governance](Governance-compendium)
| [Releases](Releases) | **[Ethereum Virtual Machine (EVM)](Ethereum-Virtual-Machine-(EVM)-Awesome-List)** |
| [FAQs](FAQs) | **[Ethereum clients, tools, wallets, dapp browsers and other projects](Clients,-tools,-dapp-browsers,-wallets-and-other-projects)** |
| [Design Rationale](Design-Rationale) | **[ÐApp Development](%C3%90App-Development)** |
| EVM intro: [Ethereum Yellow Paper](https://ethereum.github.io/yellowpaper/paper.pdf), [Beige Paper](https://github.com/chronaeon/beigepaper) and [Py-EVM](https://github.com/ethereum/py-evm) |
| [Wiki for (old) website](https://github.com/ethereum/ethereum.org/wiki) (still a good introduction) |
| [Glossary](Glossary) |


## Infrastructure
- [Chain Spec Format](Ethereum-Chain-Spec-Format)
- [Inter-exchange Client Address Protocol](ICAP:-Inter-exchange-Client-Address-Protocol)
- [URL Hint Protocol](URL-Hint-Protocol)
- [NatSpec Determination](NatSpec-Determination)
- [Network Status](Network-Status)
- [Raspberry Pi](Raspberry-Pi-instructions)
- [Exchange Integration](Exchange-Integration)
- [Mining](Mining)
- [Licensing](Licensing)
- [Consortium Chain Development](Consortium-Chain-Development)


## ÐΞV Technologies
- [RLP Encoding](RLP)
- [Node Discovery Protocol](Node-discovery-protocol)
- [ÐΞVp2p Wire Protocol](%C3%90%CE%9EVp2p-Wire-Protocol)
- [ÐΞVp2p Whitepaper](libp2p-Whitepaper) (WiP)
- [Web3 Secret Storage](Web3-Secret-Storage-Definition)
- [libp2p](https://libp2p.io/)

## Ethereum Technologies
- [Patricia Tree](Patricia-Tree)
- [Wire protocol](Ethereum-Wire-Protocol)
- [Light client protocol](Light-client-protocol)
- [Subtleties](Subtleties)
- [Solidity Documentation](https://solidity.readthedocs.io/en/latest/)
- [NatSpec Format](Ethereum-Natural-Specification-Format)
- [Contract ABI](Ethereum-Contract-ABI)
- [Bad Block Reporting](Bad-Block-Reporting)
- [Bad Chain Canary](Bad-Chain-Canary)

## Ethash/Dashimoto
- [Ethash](Ethash)
- [Ethash Yellow Paper appendix](https://ethereum.github.io/yellowpaper/paper.pdf#appendix.J)
- [Ethash C API](Ethash-C-API)
- [Ethash DAG](Ethash-DAG)

# Whisper
- [Whisper Proposal](Whisper)
- [Whisper Overview](Whisper-Overview)
- [PoC-1 Wire protocol](Whisper-Wire-Protocol)
- [PoC-2 Wire protocol](Whisper-PoC-2-Wire-Protocol)
- [PoC-2 Whitepaper](Whisper-PoC-2-Protocol-Spec)

-----
## Issues and pull requests

If you have a technical issue with a specific client, application or tool, e.g. those listed [here](Clients,-tools,-dapp-browsers,-wallets-and-other-projects), please ask in the Gitter room of that project, and if your issue is still not resolved, post an issue in the repo for that project. Please only create an issue if you can't fix it by editing yourself, it doesn't get resolved via the [Gitter documentation room](https://gitter.im/ethereum/documentation) (including pinging someone who knows how to handle the issue, or asking/finding out who knows then pinging them) and only if it is related to the wiki. 

If you had an issue that has been closed, and feel that it could be reopened after following the above steps, feel free to request to reopen it. Do not make a pull request; chances are that all PRs will be ignored, since any content in the codebase can be in this wiki instead. About 180 issues and 30 PRs were closed on May 29 2018, due to deleting the codebase and referring people to this wiki, in order to reduce the burden on maintenance by following the above steps. This fits well with Ethereum's ethos of decentralization, which includes minimising bureaucracies, and gives contributors more time to build Ethereum and satisfy the long-term interests of current and future users. If you had an issue or PR that was closed without explanation, I apologize, but it is time-consuming to reply to every one; I'm hoping that people will see the updated readme and this section.

## Contribution guidelines

### Page titles

**Careful with changing page titles!**, as the link for it will change. In particular, if you change the title for a page, any link to it will just direct to a blank page. (In the case of this page, also the Wiki tab in the header of this repo, as well as any link to the Home page, will just direct to a list of pages.) If you really want to change the title, then create a new page with the new title, move the contents of the old page to the new page, and update the old page with a redirect link to the new page. If you want to translate a page, create a new page and translate the original there. Consider previewing your changes before saving them, and if you detect any errors, fix them. If you happen to get directed to a page that doesn't exist with a prompt to create a new page, do that, without changing the title. Then check the history of the newly created page. It may be that there is a history of changes to the page that you just created, with the second most recent change (second to you creating the page) being that someone renamed the page. If so, please fix the page (restore it to the revision before the title was changed or redirect to the new page) and tag the person who renamed the page in this issue [here](https://github.com/ethereum/wiki/issues/591) or on [Gitter](https://gitter.im/ethereum/documentation).

### Wikipedia pillars

Wikipedia has [five pillars](https://en.wikipedia.org/wiki/Wikipedia:Five_pillars) which provide a good standard for contributing that we can adapt for our needs. If you have experience with editing on Wikipedia, then that will help with knowing how to edit this wiki, although the contribution rules are less strict. Referencing facts is a key writing and proofreading task, as well as checking that information is up-to-date (and updating it if otherwise), correcting grammar, typos, and spelling; and making the wiki comprehensive and easy to understand. Other rules, such as a neutral point of view and no original research are desirable, but may be hard to maintain. Notability is less relevant, this wiki is about all things Ethereum.


### License and [contributor license agreement](CC0-license#list-of-contributors)

Please permit your contributions to be under the [CC0 license](https://creativecommons.org/publicdomain/zero/1.0/legalcode) [1](https://creativecommons.org/share-your-work/public-domain/cc0/),  which makes your contributions have no rights reserved, putting them in the public domain. This will help to allow for the dissemination of information about Ethereum, the Ethereum ecosystem and Web 3 to the public, in a completely permissive manner. To state that you accept your contributions to be under a CC0 license, please add yourself to the list of external contributors [here](CC0-license#list-of-contributors). Otherwise, without adding yourself to the list, your contributions will be all rights reserved. Some previous contributions may have all rights reserved (by contributors that have not agreed to a CC0 license [at pull request 528](https://github.com/ethereum/wiki/pull/528)), since no copyright permission was stated explicitly. Until all previous contributors agree to a CC0 license, and to provide clarity of licensing, you may also wish to add a HTML comment to the top of pages or sections that you contribute to, like so: `<!--*Name Surname*, Github username, **email@domain** and/or other contact methods-->`. 

## Getting started

To get the basic concepts of Ethereum visit [http://ethereum.org](http://ethereum.org/). For another introduction targeted for end users but also for developers and others, see [here](Ethereum-introduction). If you want to get a deeper understanding, start by reading the [whitepaper](https://github.com/ethereum/wiki/wiki/White-Paper) and the [design rationale](https://github.com/ethereum/wiki/wiki/Design-Rationale). For a more formal review, read the [yellow paper](https://ethereum.github.io/yellowpaper/paper.pdf). If you are interested in being a core developer, find a project that interests you, and start contributing to that (maybe pro-bono initially, until maintainers like you and decide to hire you). For Ethereum research and protocol architecture, visit [https://ethresear.ch](https://ethresear.ch/) as well as https://github.com/ethereum/wiki/wiki/R&D. If you are interested in developing smart contracts you can see [here](https://en.wikipedia.org/wiki/Ethereum#Programming_languages), as well as under [ÐApp Development](https://github.com/ethereum/wiki/wiki/%C3%90App-Development) (which is also in the sidebar).

For getting started guides, see here

* [Step-by-Step Guide: Getting Started with Ethereum Mist Wallet](https://medium.com/@attores/step-by-step-guide-getting-started-with-ethereum-mist-wallet-772a3cc99af4)
* [Create a Hello World Contract in ethereum](https://www.ethereum.org/greeter)
* [How to create a private Ethereum network Comments Feed](https://omarmetwally.wordpress.com/2017/07/25/how-to-create-a-private-ethereum-network/)

## Downloads

See [here](Clients).

## Other Wikis

* http://ethdocs.org/en/latest/. The Homestead Guide (a historical reference, parts may be outdated).
* http://tokenengineering.net/
* https://wiki.giveth.io/

## Status / Releases / Development timeline / Roadmap

See [here](Releases).

## Don't get lost, If so look for the lost and found

If you have any question, check the [FAQS](FAQS) and [Glossary](https://github.com/ethereum/wiki/wiki/Glossary).

There are separate wikis for some implementations, as follows:

* [go-ethereum](https://github.com/ethereum/go-ethereum/wiki)
* [Parity](https://paritytech.github.io/wiki/)
* [cpp-ethereum](http://www.ethdocs.org/en/latest/ethereum-clients/cpp-ethereum/index.html)
* [pyethereum](https://github.com/ethereum/pyethereum/wiki)



