---
title: famous-bugs
description: 
published: true
date: 2020-06-30T15:26:39.359Z
tags: 
---

# Famous Bugs

Bugs that resulted in lost or stuck funds have been moved to [here](/faqs/major-issues-resulting-in-lost-or-stuck-funds.md).

## Geth Consensus Bug 
> On 2016-11-24, a consensus bug occurred due to two implementations having different behavior in the case of state reverts. [3](https://blog.ethereum.org/2016/11/25/security-alert-11242016-consensus-bug-geth-v1-4-19-v1-5-2/). The specification was amended to clarify that empty account deletions are reverted when the state is reverted... Details: Geth was failing to revert empty account deletions when the transaction causing the deletions of empty accounts ended with an an out-of-gas exception. An additional issue was found in Parity, where the Parity client incorrectly failed to revert empty account deletions in a more limited set of contexts involving out-of-gas calls to precompiled contracts; the new Geth behavior matches Parity’s, and empty accounts will cease to be a source of concern in general in about one week once the state clearing process finishes. [The source is here.](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-161.md#addendum-2017-08-15)

## DAO soft fork (prevented bug before in production)

See http://hackingdistributed.com/2016/07/05/eth-is-more-resilient-to-censorship/.

## Eclipse attack vulnerability

>  Abstract:     We present eclipse attacks on Ethereum nodes that exploit the peer-to-peer network used for neighbor discovery. Our attacks can be launched using only two hosts, each with a single IP address. Our eclipse attacker monopolizes all of the victim's incoming and outgoing connections, thus isolating the victim from the rest of its peers in the network. The attacker can then filter the victim's view of the blockchain, or co-opt the victim's computing power as part of more sophisticated attacks. We argue that these eclipse-attack vulnerabilities result from Ethereum's adoption of the Kademlia peer-to-peer protocol, and present countermeasures that both harden the network against eclipse attacks and cause it to behave differently from the traditional Kademlia protocol. Several of our countermeasures have been incorporated in the Ethereum geth 1.8 client released on February 14, 2018.
>
> What Ethereum Users Should do:    Upgrade to geth 1.8.1 . Geth versions prior to 1.8 are vulnerable. 

FMI see https://eprint.iacr.org/2018/236.pdf.