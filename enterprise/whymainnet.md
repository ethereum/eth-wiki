---
title: Why use Mainnet for Enterprise
description: 
published: true
date: 2019-11-15T15:27:48.134Z
tags: 
---

# Advantages of Mainnet
* Serendipitous interoperability.  Interoperating with other applications becomes much easier through the various [ERC standards](https://eips.ethereum.org/erc).

# Disadvantages of Mainnet
* Can't rollback.  If something embarassing happens, under a consortium chain it's possible to make a hardfork to change the state.  Using standard mainnet contracts, rollbacks aren't possible.

# FAQ
> **Is using Mainnet a privacy risk for enterprise applications?**
	Slightly more, but not by much.  Often your biggest privacy risks are from the organizations that would be part of your consortium chain (they are your biggest competitors and most motivated to glean information from your chain data!).
  
> **Is Mainnet able to handle our transaction volume?**
Varies.  It gets more complicated, but there is a variety of Layer2 scaling solutions such as the work from [Plasma Group](https://plasma.group/)(dead link).