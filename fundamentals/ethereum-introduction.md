# Ethereum Introduction

[![Documentation chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)

Due to the lightning-fast pace of development in the Ethereum space with core development and dapps continually being launched, certain parts of this article may be outdated. You can help by keeping it up to date!

## About blockchains

For an introduction to blockchains, see [this TED talk](https://www.youtube.com/watch?v=RplnSVTzvnU).

## About Ethereum

<a href="https://www.ethereum.org/" target="_blank" rel="nofollow noopener noreferrer">Ethereum</a> is a [decentralized](https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274) blockchain platform for "building unstoppable applications", while Ether is the cryptocurrency used on this platform. 

Ethereum has been described in several ways.

The simplest way to understand Ethereum is to know what it does. Just like how it is not necessary to fully understand the intricate workings of how a car works in order to appreciate it's utility, or to understand how electricity arrives in your light bulb when you turn it on, understanding the current and potential utility of Ethereum is a good start. Ethereum can be used for virtually any kind of transaction or agreement (to put it another way, any kind of activity that has an economic or governance aspect), at a lower cost than conventional alternatives, such as debit card payments, in a way that is trustless, secure, safe and censorship-resistant, all with high probability. An extensive and growing list of uses is available [here](../fundamentals/decentralized-apps-dapps.md).

<!-- TODO: Where to host PDFs -->

1.  [A Next-Generation Smart Contract and Decentralized Application Platform](https://ethereum.org/whitepaper) - Ethereum White Paper

2.  [A secure decentralised generalised transaction ledger" and a generalised "transactional singleton machine with shared-state"](https://ethereum.github.io/yellowpaper/paper.pdf).

Also described as crypto-law, and: "Ethereum, taken as a whole, can be viewed as a transaction-based state machine: we begin with a genesis state and incrementally execute transactions to morph it into some final state. It is this final state which we accept as the canonical 'version' of the world of Ethereum. The state can include such information as account balances, reputations, trust arrangements, data pertaining to information of the physical world; in short, anything that can currently be represented by a computer is admissible. Transactions thus represent a valid arc between two states; the 'valid' part is important - there exist far more invalid state changes than valid state changes. Invalid state changes might, e.g., be things such as reducing an account balance without an equal and opposite increase elsewhere. A valid state transition is one which comes about through a transaction."—Ethereum Yellow Paper

3.  [An open source "programmable blockchain"](http://ethdocs.org/en/latest/introduction/what-is-ethereum.html) — Ethdocs

4.  "[Ethereum transactions perform financial and database operations contingent on the evaluation of more complex computational scripts.](https://people.cs.uchicago.edu/~teutsch/papers/truebit.pdf)" — TrueBit

    The sources for the first and third bullet points are more general introductions, while the second is a technical introduction and specification of the Ethereum Virtual Machine. Another introduction is available [here](https://bitsonblocks.net/2016/10/02/a-gentle-introduction-to-ethereum/), but it is outdated.

Let's briefly breakdown what the terms above mean.

**Decentralized** technology uses [peer-to-peer computer networks](https://en.wikipedia.org/wiki/Peer-to-peer) (there's a picture below), and are not subject to the whims of a central authority such as a government or server administrator (like Google or Facebook) which can help to achieve better decision making for public good. **Blockchain** means that the currency is built and secured by adding and verifying blocks of transactions to blocks made previously, thus forming a "chain". Blocks added to the chain become harder and harder to crack over time, as they are verified by more nodes in the blockchain peer-to-peer network. Blockchain technology has been referred to as the **Web 3.0**. The world wide web (retroactively the Web 1.0) consisted of websites publishing content and users passively reading/viewing it. The Web 2.0 used user interaction, such as forums (with upvoting and commenting), reaction buttons (e.g. the Facebook reactions: likes 👍, love ❤️ , laughter 😆, wow 😲, sad 😢, angry 😠), sharing (republishing), however these interactions have no direct economic effect on the host website; users do not share in the value generated from the website. The Web 3.0 is starting to be defined as the movement away from centralization of computation power in servers which provide services to clients (known as the <a href="https://en.wikipedia.org/wiki/Client%E2%80%93server_model" target="_blank" rel="noopener">client-server network model</a>) to peer-to-peer networks and blockchains, and <a href="https://github.com/DemocracyEarth/paper/blob/master/README.mediawiki" target="_blank" rel="noopener">from centralisation of authority and sovereignty from nation-states and corporations to the networked individual</a>.

<!-- TODO: Fix images -->

![server-based-network](https://sustergy.files.wordpress.com/2017/05/200px-server-based-network-svg.png)

![p2p-network](https://sustergy.files.wordpress.com/2017/05/200px-p2p-network-svg.png)

**Cryptocurrency** refers to a digital currency that secures transactions with cryptographic code, which is solved through hardware computational power (known as mining or proof of work) or other less energy-intensive ways such as proof-of-stake. (There are more details on that below.)

Zero knowledge proofs like <a href="https://crypto.stackexchange.com/questions/19884/what-are-snarks" target="_blank" rel="noopener">ZK SNARKs</a> can also be used to make cryptocurrency transactions more private 🕵️ or secret 🤐 (which is different to being secure 🔒), thus negating the need to run applications on a permissioned private network like the [Ethereum Enterprise Alliance](https://entethalliance.org/). Ethereum uses [precompiled contracts for addition and scalar multiplication on the elliptic curve alt_bn128](https://github.com/ethereum/EIPs/pull/213), for [pairing checks](https://github.com/ethereum/EIPs/pull/212), which permit [zk-SNARKs](https://blog.ethereum.org/2017/10/12/byzantium-hf-announcement/), also see [here](https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6), [as implemented](https://github.com/ethereum/EIPs#finalized-eips-standards-that-have-been-adopted) in the [Byzantium hard fork](https://blog.ethereum.org/2017/10/12/byzantium-hf-announcement/). There is also the Zerocoin protocol which is demonstrated by <a href="https://zcoin.io/" target="_blank" rel="nofollow noopener noreferrer">Zcoin</a> (which plans to integrate Ethereum).

## History

Here is a blog post from Vitalik Buterin, the founder of Ethereum, on [Ethereum pre-history](https://vitalik.ca/2017-09-15-prehistory.html). [Here](https://blog.ethereum.org/2016/02/09/cut-and-try-building-a-dream/) is another blog post with more history.

## Uses

The platform part of Ethereum makes it much more useful than just a cryptocurrency. With it, you can create any decentralized application (known as a dapp, which works over a peer-to- peer network rather than a centralized client-server network 💻🕸️), so the functionality is only limited by what programs could potentially do and not do, and by consequence, what programmers develop, 👨‍💻 but it can theoretically be used for any economic or governance activity.

### List of dapps

For a list of dapps, visit [here](../fundamentals/decentralized-apps-dapps.md). 

## Market analysis

Assessing the actual usage of blockchains is a more reliable indicator than the market cap. <http://blocktivity.info/> provides data to do that.

<!-- TODO: Update data below -->

As of the 9th of January 2018, [the market capitalisation of Ethereum is $118.5 billion USD](https://cryptolization.com/ethereum) (refer to the link for the latest figure), and [it has been in circulation since 30 July 2015](../roadmap/releases.md), with the [first transaction](https://www.reddit.com/r/ethereum/comments/6qildp/what_is_the_first_ever_ethereum_transaction/) after the [genesis block](https://etherscan.io/block/0) using Ethereum on [7 August 2015](https://etherscan.io/block/46147). Compare this with the next largest and the current largest cryptocurrency, [Bitcoin, with a market cap of $253.0 billion USD](https://cryptolization.com/ethereum), where [it has been in circulation since January 2009](http://www.newyorker.com/reporting/2011/10/10/111010fa_fact_davis). Technically, Ethereum has had a much faster growth rate, while more importantly for long term investment (I do not encourage speculation or buying with capital that you can't afford to lose, without due diligence as that only causes volatility as has been seen) the fundamentals are much better than Bitcoin. While it is true that Bitcoin has more of a market and currency, e.g. in terms of more entities that will accept it as a form of payment, the creator of this wiki expects that time will change that (indeed the <a href="https://seekingalpha.com/article/4077679-ethereum-blasts-20-billion-market-cap-half-bitcoin" target="_blank" rel="noopener">market cap of Ethereum recently surpassed half that of Bitcoin, around May 2017</a>). Also, [the number of transactions of Ethereum surpassed that of several cryptocurrencies combined on 22 Nov 2017](https://www.reddit.com/r/ethereum/comments/7est9k/ethereum_is_now_processing_more_transactions_a/). However, note [this retort](https://www.reddit.com/r/ethereum/comments/7est9k/ethereum_is_now_processing_more_transactions_a/dq7a31u/).

## Issues

There also several issues with Ethereum, such as not being scalable enough, not being fully decentralized, energy consumption with mining and quantum computing attacks. With its [large storage database](https://www.reddit.com/r/ethtrader/comments/7axn5g/ethereum_blockchain_sizewe_have_a_problem/) (I have to provide a [Reddit link](https://www.reddit.com/r/ethtrader/comments/7axn5g/ethereum_blockchain_sizewe_have_a_problem/) as a source as the [original link](https://etherscan.io/chart/chaindatasizefull) doesn't have the graph any more, while [Wayback doesn't render it either](https://web.archive.org/web/20171211015955/https://etherscan.io/chart/chaindatasizefull)), mining and architecture requiring to run a full node to mine or validate transactions, it is not decentralized enough. More (outdated but still applicable) info on that is e.g. [here](https://ethereum.stackexchange.com/questions/143/what-are-the-ethereum-disk-space-needs#826), as well as [here](https://github.com/ethereum/go-ethereum#full-node-on-the-main-ethereum-network).

## Scalability

Ethereum will need to scale to process far more transactions per second (to become a "<a href="https://www.youtube.com/watch?v=j23HnORQXvs" target="_blank" rel="noopener">world computer</a>") than Visa, Mastercard and American Express combined (which process on the order of [tens of thousands of transactions per second](https://usa.visa.com/run-your-business/small-business-tools/retail.html) [in the link, CTRL+F 24,000]), while Ethereum 1.0, the current version as of December 30 2017, processed [a record of 1103523 transactions on Friday, December 22, 2017, or 12.77 transactions per second](https://web.archive.org/web/20171230005127/https://etherscan.io/chart/tx).

Note that [Ripple claims that it's Consensus Ledger can process a thousand transactions per second](https://ripple.com/dev-blog/ripple-consensus-ledger-can-sustain-1000-transactions-per-second/), while it could process more with payment channels. "Although payment channels achieve practically infinite scalability by decoupling payment from settlement, they do so without incurring the risk typically associated with delayed settlement." Further note that Ripple achieves this by trading off on decentralization, through a [distributed network of validators or distributed servers](https://ripple.com/build/xrp-ledger-consensus-process/), while it has been described as a [federation protocol](https://wiki.ripple.com/Federation_protocol).

There are even more scalable blockchains that use a delegated proof of stake (DPOS) consensus protocol, such as Bitshares and Steem. [Bitshares can apparently process 100,000 TPS](https://bitshares.org/technology/industrial-performance-and-scalability/).

More generally, in order to have faster payments or higher transaction throughput, you need to reduce the number of validators (miners are a kind of validator that perform energy intensive computational work, finding a random nonce or sequence number in a large set of numbers) in the consensus protocol, or reduce the other (i.e. for faster payments you can reduce transaction throughput or reduce validators, while for higher transaction throughput you can reduce validators or have payments take longer to finalize). This is [a trade-off triangle](https://twitter.com/VladZamfir/status/932319930363494400). You could potentially have one blockchain with [heterogeneous sharding](https://twitter.com/VladZamfir/status/932320997021171712), with different shards with a different degree of balance between these properties. Ethereum is working on [sharding](https://ethresear.ch/t/sharding-phase-1-spec/1407/26).

If you increase scalability in an instant via some blockchain or shard, while keeping latency constant (or reducing it) you need to reduce decentralization, which reduces the number of points of attack needed to compromise the whole network, i.e. reducing decentralization reduces security.

## Volatility

Ethereum and all cryptocurrencies (except for USDT and DAI) have a lot of [volatility](https://twitter.com/JamesCRay01/status/959595937856303104), [particularly](https://twitter.com/JamesCRay01/status/953506845015994368) during news events such as banning [individual companies that don't register with the local securities authority but are selling a security](https://twitter.com/leashless/status/941501389687214081), bans on all ICOs or cryptocurrencies, bugs (see below) or geopolitical tensions such as between the [North Korea and the US and South Korea](https://twitter.com/JamesCRay01/status/938926302525980673), with missile launch tests from the former and large-scale military drills from the latter two. Non-stable cryptos tend to drop when there is news that governments ban or may ban ICOs or trading of cryptocurrencies, e.g. with [China](https://t.co/E0FDsBzk01), [Brazil](https://t.co/361eAPRSBU), [South Korea](https://t.co/lVe8VIafIO), Europe and the US. On the other hand, other countries like Saudi Arabia and [Australia](https://t.co/zFza3AV6Hm) have been very supportive of cryptocurrencies. Non-stable cryptos tend to rise when there is news of geopolitical tensions, or just politicians making bad decisions. NSCs have dropped in price when there are issues with exchanges, such as [being](https://www.wired.com/2014/03/bitcoin-exchange/) [hacked](https://bravenewcoin.com/news/fourth-largest-bitcoin-exchange-bithumb-hacked-for-billions-of-won/), [flash crashes](https://twitter.com/JamesCRay01/status/939014321006305281), or just [closing down](https://t.co/WOIQPCbBzr).

The biggest risk with cryptocurrencies is not so much from actors within the ecosystem such as mining/validator attacks, **scams** (note that there is no substitute for due diligence, but you can use scam checkers such as this site [here](https://fried.com/crypto-scam-checker/) and exchange issues), but from regulators doing blanket bans on ICOs or more broadly, cryptocurrency trading. But this isn't reasonable (certainly not as a permanent ban) as they are useful for governments as well. Governments may also want to regulate or ban cryptocurrencies as they perceive them as a threat to devaluing their fiat currencies (but this can be offset through regulation, taxation, etc.), as well as a potential tool for tax evasion (but this can be regulated e.g. with KYC). There is also the major risk that people buy into it without really understanding it and/or with non-risk capital, and then sell it off when bad news events occur.

Note also that with stable cryptocurrencies, the price can't rise anywhere nearly fast as cryptocurrencies, as well as not being able to drop anywhere nearly as fast. So stable cryptocurrencies are more suitable as a store of value, but may not rise in value as much in the very long-term (e.g. over a year).

More news:

-   [China to stamp out cryptocurrency trading completely with ban on foreign platforms](http://www.scmp.com/business/banking-finance/article/2132009/china-stamp-out-cryptocurrency-trading-completely-ban)
-   [More Crypto Bans: Lloyds Shuts Down Credit Card Purchases](https://cryptocurrencynews.com/business/banking/[lloyds-credit-card-purchases-crypto-bans/)

## Energy consumption and centralization with Proof of work vs proof of stake

The mining process to crack cryptographic code (specifically to discover the nonce, a very large number, for each block by trial and error) requires a lot of computation power. Nevertheless, I'm guessing that the computation power should be less when you consider the <strong>energy consumption</strong> of incumbent financial systems. (Think of extracting and processing resources to make coins and notes, minting and printing, energy consumption of banks and tiers of related energy consumption in the life cycle of fiat money.) Still, developers of some cryptocurrencies such as Ethereum are transitioning to (as is the case for Ethereum), or already using, a different way of maintaining and creating blocks, known as proof of stake. For more information, you can see this Proof of Stake Wikipedia article <a href="https://en.wikipedia.org/wiki/Proof-of-stake" target="_blank" rel="nofollow noopener noreferrer">here</a> (although note the header warning about the article potentially not being verifiable or neutral due to relying heavily on sources too closely associated to the subject). The tricky part is in getting proof methods to work better than proof of work, as outlined <a href="https://en.wikipedia.org/wiki/Proof-of-stake" target="_blank" rel="noopener">here</a> in the criticism section of the PoS Wiki. For more information about PoS, see Casper [The Friendly Finality Gadget](https://github.com/ethereum/research/tree/master/papers/casper-basics) for PoS validation with Proof-of-Work (PoW), [Casper The Friendly Ghost: CBC](https://github.com/ethereum/research/blob/master/papers/CasperTFG/CasperTFG.pdf) for full Proof-of-Stake (PoS) and a [testnet](https://hackmd.io/s/Hk6UiFU7z).

## Quantum computing attacks

If quantum computing becomes more performant Ethereum's cryptographic signature scheme, Elliptic Curve Digital Signature Algorithm (ECDSA), would be insecure. However, there are solutions for this that will be implemented soon in the [Constantinople release](Releases) with [EIP 86: Abstraction of transaction origin and signature, which has "**Custom cryptography**: users can upgrade to ed25519 signatures, Lamport hash ladder signatures or whatever other scheme they want on their own terms; they do not need to stick with ECDSA." Lamport signatures could be used in a quantum resistant algorithm](https://github.com/ethereum/EIPs/pull/208). More info on that is e.g. [here](https://ethereum.stackexchange.com/a/13577/95840)), [here](https://blog.ethereum.org/2015/12/24/understanding-serenity-part-i-abstraction/), and [here](./../howto/ethereum-development-tutorial.md).

## No technological artefacts can be a panacea

For the continual improvement of humanity, there needs to be balance in life between things that benefit us materially and things that benefit us on higher levels, particularly spiritually. There is a risk that technology can make some people better off, and others worse off. So there needs to be consideration for how technology can be implemented to maximise [utility](https://en.wikipedia.org/wiki/Utilitarianism).  One consideration of that is [here](https://medium.com/@RhysLindmark/co-evolving-the-phase-shift-to-cryptocapitalism-by-founding-the-ethereum-commons-co-op-f4771e5f0c83), which looks at using Ethereum to establish a global commons (including infrastructure, healthcare, education and universal basic income) with voluntary contributions or a tax on transactions.

## Bugs

Ethereum has had expensive bugs, such as those listed [here](../faqs/major-issues-resulting-in-lost-or-stuck-funds.md) and [here](../faqs/famous-bugs.md).

## How do you buy and sell Ether, the currency of Ethereum?

Refer to [here](./getting-ether.md).

## Development

Are you interested in learning to develop smart contracts with Ethereum, and develop a really useful dapp and become a millionaire?

Check out the [Ethereum website](https://www.ethereum.org/)! Then, you can [read the Solidity docs](https://solidity.readthedocs.io/en/latest).

If you want to help contribute to core development, there is also:

-   the [Yellow Paper](https://github.com/ethereum/yellowpaper);
-   [Beige Paper](https://github.com/chronaeon/beigepaper); and
-   [Py-EVM](https://github.com/ethereum/py-evm).
-   [Geth (Go implementation)](https://github.com/ethereum/go-ethereum)

## Core development

-   [client development](../clients/clients-tools-dapp-browsers-wallets-and-other-projects.md);
-   if you're interested in testing, see the documentation [here](https://ethereum-tests.readthedocs.io/en/latest/), as well as [the Github tests repo](https://github.com/ethereum/tests), [a Gist here (it is outdated)](https://gist.github.com/Souptacular/fd197b1fac7c6d2660b0bef27a33ed40#lll-and-evm-stack-resources),  and [Gitter here](https://gitter.im/ethereum/tests);
-   documentation and specification review, e.g. (and in particular) of [EIPs](https://github.com/ethereum/EIPs); 
-   [many other repositories](https://github.com/ethereum).

For R&D, refer to [here](../research/rd.md).

## Programming languages

-   Learn Python first, e.g. with [Learn Python the Hard Way](https://www.learnpythonthehardway.org/) (I learnt using this, but it's rather condescending, so I'd recommend [Pydocs](https://docs.python.org/3/) instead). There's others, e.g. [Codecademy](https://www.codecademy.com/learn/learn-python), and [Coursera](https://www.coursera.org/courses?languages=en&query=learn+python), etc. Knowing Python is useful for research and demonstration, with demonstration e.g. for [client development](../clients/clients-tools-dapp-browsers-wallets-and-other-projects.md), e.g. for [Py-EVM](https://github.com/ethereum/py-evm) which is being used as an Ethereum client, to implement statelessness and sharding, as well as [vyper](https://github.com/ethereum/Vyper), an experimental, secure, smart contract programming language;
-   [LLL](https://media.consensys.net/an-introduction-to-lll-for-ethereum-smart-contract-development-e26e38ea6c23) (also see [here](https://github.com/ethereum/solidity/tree/develop/liblll) and [here](https://github.com/ethereum/solidity/tree/develop/lllc));
-   [JULIA](https://solidity.readthedocs.io/en/develop/julia.html), an intermediate language for different Ethereum virtual machines;

## Concluding remarks

Ether certainly seems like a good investment, and a good alternative to using fiat currencies, as well as an enabler for otherwise uneconomical business, due to lower transaction costs. It's more decentralized nature than central banks has advantages for trade from a local to global scale. With governance applications and systems on top Ethereum, it is even possible to do away with the hindering borders surmounted by nation-states. By doing away with these borders, society can be more open, inclusive and equitable.

However, all technology can only help mankind and the world to a certain extent. What is more important is for each and every person to become increasingly blissful. Each person must go within and enter a stillness of body and mind, which is when that bliss starts to manifest, and practice balanced living. Practicing certain techniques such as those given by Self-Realization Fellowship, such as daily Kriya yoga meditation, developing unconditional love that starts in the heart, keeping the mind at the point between the eyebrows, and moral living, helps each person manifest that bliss within, and from there, express that bliss outwardly at all times.

## Further reading

-   [Another introduction](https://github.com/jamesray1/Ethereum-introduction/wiki/Ethereum-introduction)
-   [MyEtherWallet knowledge base (good for issues with wallets)](https://myetherwallet.github.io/knowledge-base/)
-   [An introduction (Frontier first release, outdated)](https://ethereum.gitbooks.io/frontier-guide/content/ethereum.html)
-   [Here's another introduction, made in November 2017](https://medium.com/@Ethereum_AI/ethereum-introduction-what-exactly-is-it-why-care-how-to-invest-9a627ab04408)
-   [Ethereum community on Gitter](https://gitter.im/ethereum)
-   [Ethereum Wikipedia article](https://en.wikipedia.org/wiki/Ethereum)
-   [Ethereum and the hodlers that love them](https://www.reddit.com/r/ethtrader/comments/6jyn9y/ethereum_the_hodlors_that_love_them/)
-   This article was originally created here in May 2017, and has been regularly updated since then: <https://sustergy.wordpress.com/2017/05/18/why-buy-ether-and-how/>. Feel free to send a donation to the initial author at jamesray.eth, or make edits to it yourself, or fork it!

## More resources

<https://blockbyblock.io/resources>
