<!-- TITLE: Getting Ether -->



[![Documentation
chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)

> Outlines how to get Ether.

Note that you should only buy Ether (or any cryptocurrency except for
stable ones like DAI or USDT) with risk capital, i.e. money that you can
afford to lose, because of the volatile nature of Ether.

In order to obtain Ether, you need to either:

-   trade other currencies for ether using centralised or trustless
    services
-   not recommended as it\'s not very user friendly: use the user
    friendly [Mist Ethereum GUI
    Wallet](https://github.com/ethereum/mist/releases) that as of Beta 6
    introduced the ability to purchase ether using the
    <http://shapeshift.io/> API.
-   not recommended: become an Ethereum miner (see
    [here](https://forum.ethereum.org/discussion/8886/quick-start-guide-to-mine-ethereum/p1).
    Note that
    [this](https://ethereum-homestead.readthedocs.io/en/latest/mining.html)
    Homestead guide is outdated, which is the same as
    [this](http://wikijs.ethereum.wiki/Mining) mining wiki).
    However, this is not recommended as Ethereum is going to transition
    to proof-of-stake, making mining obsolescent. Becoming a miner would
    involve investing in a mining rig (several GPUs, plus maybe other
    hardware if needed, like a compatible computer), which is unlikely
    to get a return on investment before PoS is implemented.

After you get Ether it is recommended that you transfer it to a wallet
which you have the private key for, such as
[MyEtherWallet](https://myetherwallet.com) or
[MyCrypto](https://www.mycrypto.com/). Then to use Ether to make
transfers [MetaMask](https://metamask.io/) (a browser extension which
allows Ethereum dApps to be run through your browser) is recommended.

Trustless services
==================

Note that the Ethereum platform is special in that the smart contracts
enable trustless services that obviate the need for trusted third
parties in a currency exchange transaction, i.e. disintermediate
currency exchange businesses. Note that these services may still require
some level of trust, e.g. in the service provider.

Projects that have launched includes:

-   Those listed in this [Etherscan
    chart](<https://etherscan.io/stat/dextracker>).
-   [LocalEthereum](https://localethereum.com/) allows exchanging Ether
    for fiat currencies, like [Localbitcoin](https://Localbitcoin.com/).
    \"The smart contract allows users to safely exchange ether with one
    another, and to name a trusted third-party to mediate a trade if a
    dispute arises. Currently, the trusted mediator is always
    localethereum.com, but the contract will be adapted in the future to
    switch over to a reputation-based distributed arbitrator pool.\" The
    source of this quote is
    [here](https://blog.localethereum.com/how-our-escrow-smart-contract-works/).
-   [EtherDelta](https://etherdelta.com). I (James Ray) found that the
    charts on the site weren\'t very good on January 1, 2017, so I sent
    a [tweet giving
    feedback](https://twitter.com/JamesCRay01/status/953101168669999104).
    This is good for trading tokens. Unfortunately I tried to make a
    deposit with a small amount, so that I could then buy a token but
    nothing happened.
-   [ForkDelta](https://forkdelta.github.io) claim to have \"a ton of
    improvements including a much faster order processing system. It
    interacts with ForkDelta\'s revamped API and EtherDelta\'s original
    contract.\"
-   [Trade Ogre](https://tradeogre.com/markets) apparently are fast and
    have low fees, but they don\'t have many tokens listed.
-   [Next.Exchange](https://next.exchange/) call themselves a hybrid
    decentralized crypto exchange, although it is vague/unclear how
    their exchange model works.

Projects that have not been released yet (as of Dec 14 2017) includes:

-   

    [BTCrelay](http://btcrelay.org/)

    :   -   [More
            information](https://medium.com/@ConsenSys/taking-stock-bitcoin-and-ethereum-4382f0a2f17)
            (about ETH/BTC 2-way peg without modifying bitcoin code).
        -   [BTCrelay
            audit](http://martin.swende.se/blog/BTCRelay-Auditing.html)

List of centralised exchange marketplaces
=========================================

  Exchange       Currencies
  -------------- -------------------------
  Poloniex       BTC
  Kraken         BTC, USD, EUR, CAD, GBP
  Gatecoin       BTC, EUR
  Bitfinex       BTC, USD
  Bittrex        BTC
  Bluetrade      BTC, LTC, DOGE
  HitBTC         BTC
  Livecoin       BTC
  Coinsquare     BTC
  Bittylicious   GBP
  BTER           CNY
  Yunbi          CNY
  Metaexchange   BTC

You can also search for \"\<insert your country\> Ether exchange\".

There\'s also this:
<https://myetherwallet.github.io/knowledge-base/faq/buying-selling-exchanging-eth-tokens-fiat.html>.
For further info (which lists more exchanges), see
[here](http://wikijs.ethereum.wiki/Getting-Ether:-further-info).

Centralised fixed rate exchanges
================================

  Exchange                       Currencies
  ------------------------------ --------------------------------
  [Shapeshift](shapeshift.io)    BTC, LTC, DOGE, Other
  [Karsha](https://karsha.biz)   75+ Crypto/ERC20, 3 Fiat (USD)
  [Bity](https://bity.com)       BTC, USD, EUR, CHF

Trading and price analytics
===========================

-   [ETH markets exhaustive listing by volume on
    coinmarketcap](https://coinmarketcap.com/currencies/ethereum/#markets)
-   Aggregating realtime stats of major ETH markets:
    -   [Tradeblock](https://tradeblock.com/ethereum)
    -   [EthereumWisdom](http://ethereumwisdom.com)
    -   [Cryptocompare](https://www.cryptocompare.com/coins/eth/overview)
    -   [Coinmarketcap](https://coinmarketcap.com/currencies/ethereum/)
-   [EthGasStation](https://ethgasstation.info) is useful for checking
    the gas price to set before making a transaction lists, as well as
    checking [Gas Guzzlers, or the \'Top 10 ETH Contracts By Transaction
    Count Over the Last 1,500
    Blocks\'](https://ethgasstation.info/gasguzzlers.php)

Online wallets, paper wallets, and cold storage {#online-wallets-and-storage-solutions}
-----------------------------------------------

::: {.todo}
This is here just a dumping ground of links and notes Please move this
over in a listing form to ecosystem

Keep examples here, maybe explain paranoid practices, list dangers
:::

-   

    Mist Ethereum Wallet

    :   -   [Releases to
            download](https://github.com/ethereum/mist/releases)
        -   [Mist Ethereum Wallet developer
            preview](https://blog.ethereum.org/2015/09/16/ethereum-wallet-developer-preview/) -
            foundation blog post
        -   [How to easily set up the Ethereum Mist
            wallet!](https://www.youtube.com/watch?v=Z6lE0Ctaeqs) -
            Tutorial by Tommy Economics

-   

    Kryptokit Jaxx

    :   -   [Jaxx main site](http://jaxx.io/)
        -   [Mobile
            release](http://favs.pw/first-ethereum-mobile-app-released/#.VsHn_PGPL5c)

-   

    Etherwall

    :   -   [Etherwall website](http://www.etherwall.com/)
        -   [Etherwall source](https://github.com/almindor/etherwall)

-   

    MyEtherWallet

    :   -   [MyEtherWallet website](https://www.myetherwallet.com/)
        -   [MyEtherWallet
            source](https://github.com/kvhnuke/etherwallet/)
        -   [Chrome
            extension](http://sebfor.com/myetherwallet-chrome-extension-release/)

-   

    Cold storage

    :   -   [Icebox](https://github.com/ConsenSys/icebox) by
            [ConsenSys](https://consensys.net/) - Cold storage based on
            lightwallet with HD wallet library integrated.
        -   [Reddit discussion
            1](https://www.reddit.com/r/ethereum/comments/45uvmy/offline_cold_storage_question/offline_cold_storage_question)
        -   [How to setup a cold storage
            wallet](https://www.reddit.com/r/ethereum/comments/48wfbv/eli5_how_to_setup_a_cold_storage_wallet_as/)

-   

    Hardware wallet

    :   -   [reddit discussion
            2](https://www.reddit.com/r/ethereum/comments/45siaq/hardware_wallet/)
        -   [reddit discussion
            3](https://www.reddit.com/r/ethereum/comments/4521o4/crowdfunding_ethereum_hardware_cold_storage_wallet/)

-   

    Brain wallet

    :   -   brain wallets are not safe, do not use them.
            <https://www.reddit.com/r/ethereum/comments/45y8m7/brain_wallets_are_now_generally_shunned_by/>
        -   Extreme caution with brain wallets. Read the recent
            controversy:
            <https://reddit.com/r/ethereum/comments/43fhb5/brainwallets>
            vs
            <http://blog.ether.camp/post/138376049438/why-brain-wallet-is-the-best>

-   

    Misc

    :   -   [Kraken Wallet Sweeper Tool](https://www.kraken.com/ether) -
            Pre-sale wallet import
        -   [Recommended ways to safely store
            ether](http://ethereum.stackexchange.com/questions/1239/what-is-the-recommended-way-to-safely-store-ether)
        -   [How to buy and store
            ether](http://sebfor.com/how-to-buy-and-store-ether/)
        -   [A laymen\'s intro into brute forcing and why not to use
            brain
            wallets](http://www.fastcompany.com/3056651/researchers-find-a-crack-that-drains-supposedly-secure-bitcoin-wallets)
        -   [Pyethsaletool](https://github.com/ethereum/pyethsaletool/blob/master/README.md)
        -   [Account vs
            wallet](https://www.reddit.com/r/ethereum/comments/47j3r5/eli5_accounts_vs_wallet_contracts_on_mist/)
