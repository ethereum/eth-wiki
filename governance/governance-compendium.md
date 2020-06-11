---
title: Governance Compendium
description: 
published: true
date: 2020-06-11T13:31:59.848Z
tags: 
---

[![governance](https://badges.gitter.im/governance.svg)](https://gitter.im/ethereum/governance)
[![Documentation chat](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ethereum/documentation)

![governance flowchart](https://pbs.twimg.com/media/DcKW-GlXUAAMsR0.jpg)

## Sources:
* [EIPs](https://github.com/ethereum/eips): Ethereum Improvement Proposals
* [Ethereum Magicians](https://ethereum-magicians.org/): for technical governance
* [Gitter room for Ethereum governance](https://gitter.im/ethereum/governance)
* [ethereum/pm](https://github.com/ethereum/pm): project management for the All Core Devs Meeting. "The all core devs meeting is a technical meeting intended to bring together various Ethererum teams who play major roles in determining the direction of the protocol. Ethereum client and research teams provide updates to their projects, discuss various EIPs to improve the protocol, and support each other as we buidl Web 3.0."
* [EIP-0](https://twitter.com/hashtag/EIP0?src=hash): for the philosophical and ethical part of governance + [an all devs video](https://www.youtube.com/watch?v=VJ3r52T7HV8) and [AMA video](https://www.youtube.com/watch?v=LcBqypKbYMA) + [Youtube summaries and Reddit comments](https://www.reddit.com/r/ethereum/comments/8ggrgo/join_the_ethereum_governance_ama_at_the_eip0/)
* [governance chapter for Mastering Ethereum](https://github.com/lrettig/ethereumbook/blob/governance/contrib/governance.asciidoc)
* [Vlad Zamfir's talk about governance](https://ethereum-magicians.org/t/vlad-zamfirs-ethcc-talk-about-governance/78)

## Against on chain governance:
* [blog post from Vlad](https://medium.com/@Vlad_Zamfir/against-on-chain-governance-a4ceacd040ca). Snippets: "On-chain governance makes node operator participation in governance completely unnecessary." However, node operator participation is necessary for the current protocol. Thus, changing to on-chain governance is very risky. "Unless there are governance processes that get _Sybil-resistant_ input from node operators, on-chain governance therefore always has the potential to disenfranchise node operators (and users) of the blockchain." [Vlad's reply to a comment to this post](https://medium.com/@Vlad_Zamfir/its-only-just-a-design-problem-da3806ff5114).
* [Vitalik's post on plutocracy](https://vitalik.ca/general/2018/03/28/plutocracy.html)

## Projects working on blockchain governance:
- [Democracy Earth](http://democracy.earth/): it is "an open source and decentralized democratic governance protocol for any kind of organization. It "uses proof of identity for sybil resistance via blockchain birth certificates, proof of attention, quadratic voting and liquid democracy; governance platform for an organization of any size). 
- [Aragon](https://aragon.one/):

> Aragon is a project that aims to disintermediate the creation and maintenance of organizational structures by using blockchain technology. We want to empower people across the world to easily and securely manage their organizations. We provide the tools for anyone to become an entrepreneur and run their own organization, to take control of their own lives
>
> By making it possible for everyone in the world to organize, we are enabling a borderless, permissionless and more efficient creation of value

 - [EthSignals.org](https://www.ethsignals.org) – Working group on improving Ethereum Governance with better signalling. Support the [tennagraph.com](tennagraph.com) – dapp for stances collection around EIPs.


While the following projects do not have blockchain governance as a mission, they do relate to governance or deliberately use or plan to use governance mechanisms:

- [Maker DAO](https://makerdao.com/) a stablecoin that uses a utility and governance volatile MKR token, for holders to use in governing the DAI stable coin
- [Havven](https://havven.io): another stablecoin that involves issuing tokens against a distributed collateral pool. James Ray's opinion: this seems simpler than DAI, while also intuitively seeming to be more desirable. See e.g. [this Twitter thread](https://twitter.com/JamesCRay01/status/1046893184800841728) for a related proposal to issue a token against a distributed pool of _ethical_ assets, which should result in less downside volatility and more upside volatility or potential for growth.
- [Pocket Network](http://pokt.network/). A decentralized blockchain which incentivizes running a full node and relaying transactions, supporting connecting to blockchains. See also https://ethresear.ch/t/incentivizing-full-state-nodes-as-an-api-service/2835/1, which has a link to their [white paper](https://ethresear.ch/uploads/default/original/2X/b/b662eec0f686f44f504eb49e69760fca42535682.pdf).

## Mechanism design

Infographic: https://twitter.com/VladZamfir/status/1014882947781087233

It's important to try to match rewards in protocol as closely as possible with the true utility provided, which isn't done well with a volatile cryptocurrency. Protocol participants have external incentives such as capital costs.

## Liberal Radicalism

https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3243656

An alternative societal funding mechanism to capitalism and representative democracy that provides (near) optimal funding provision of public goods. Related to governance because governance is often concerned with allocating a budget.