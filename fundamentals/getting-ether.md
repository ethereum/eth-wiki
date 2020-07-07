---
title: getting-ether
description: 
published: true
date: 2020-07-07T15:18:33.823Z
tags: 
---

# Getting Ether

[![Documentation
chat](https://img.shields.io/badge/gitter-Docs%20chat-4AB495.svg)](https://gitter.im/ethereum/documentation)

> Outlines how to get Ether.

Note that you should only buy Ether (or any cryptocurrency except for
stable ones like DAI or USDT) with risk capital, i.e. money that you can
afford to lose, because of the volatile nature of Ether.

<!-- TODO: This needs huge amount of updating -->

In order to obtain Ether, you need to either:

-   trade other currencies for ether using centralised or trustless
    services
-   not recommended as it's not very user friendly: use the user
    friendly [Mist Ethereum GUI Wallet](https://github.com/ethereum/mist/releases) that as of Beta 6
    introduced the ability to purchase ether using the [ShapeShift API](http://shapeshift.io/).
-   **not recommended**: become an Ethereum miner (see
    [here](https://forum.ethereum.org/discussion/8886/quick-start-guide-to-mine-ethereum/p1).
    Note that
    [this](https://ethereum-homestead.readthedocs.io/en/latest/mining.html)
    Homestead guide is outdated, which is the same as
    [this](./mining.md) mining wiki).
    However, this is not recommended as Ethereum is going to transition
    to proof-of-stake, making mining obsolescent. Becoming a miner would
    involve investing in a mining rig (several GPUs, plus maybe other
    hardware if needed, like a compatible computer), which is unlikely
    to get a return on investment before PoS is implemented.

After you get Ether it is recommended that you transfer it to a wallet
which you have the private key for, such as
[MyEtherWallet](https://myetherwallet.com), [MyCrypto](https://www.mycrypto.com/), [Guarda Wallet](https://guarda.co), or [others](https://ethereum.org/wallets/). Then to use Ether to make
transfers [MetaMask](https://metamask.io/) (a browser extension which
allows Ethereum dApps to be run through your browser) is recommended.

## Trustless services

<!-- TODO: Check all below -->

Note that the Ethereum platform is special in that the smart contracts
enable trustless services that obviate the need for trusted third
parties in a currency exchange transaction, i.e. disintermediate
currency exchange businesses. Note that these services may still require
some level of trust, e.g. in the service provider.

Projects that have launched includes:

-   Those listed in this [Etherscan chart](https://etherscan.io/stat/dextracker).

-   [LocalEthereum](https://localethereum.com/) allows exchanging Ether
    for fiat currencies, like [Localbitcoin](https://Localbitcoin.com/).

    "The smart contract allows users to safely exchange ether with one
    another, and to name a trusted third-party to mediate a trade if a
    dispute arises. Currently, the trusted mediator is always
    localethereum.com, but the contract will be adapted in the future to
    switch over to a reputation-based distributed arbitrator pool." [Quote source](https://blog.localethereum.com/how-our-escrow-smart-contract-works/).

-   [EtherDelta](https://etherdelta.com). I (James Ray) found that the
    charts on the site weren't very good on January 1, 2017, so I sent
    a [tweet giving feedback](https://twitter.com/JamesCRay01/status/953101168669999104).
    This is good for trading tokens. Unfortunately I tried to make a
    deposit with a small amount, so that I could then buy a token but
    nothing happened.

-   [ForkDelta](https://forkdelta.github.io) claim to have 

    "a ton of
    improvements including a much faster order processing system. It
    interacts with ForkDelta's revamped API and EtherDelta\\'s original
    contract."

-   [Trade Ogre](https://tradeogre.com/markets) apparently are fast and
    have low fees, but they don't have many tokens listed.

-   [Next.Exchange](https://next.exchange/) call themselves a hybrid
    decentralized crypto exchange, although it is vague/unclear how
    their exchange model works.

<!-- TODO: Update -->

Projects that have not been released yet (as of Dec 14 2017) includes:

-   [BTCrelay](http://btcrelay.org/)
    -   [More information](https://medium.com/@ConsenSys/taking-stock-bitcoin-and-ethereum-4382f0a2f17)
         (about ETH/BTC 2-way peg without modifying bitcoin code).
    -   [BTCrelay audit](http://martin.swende.se/blog/BTCRelay-Auditing.html)

## List of centralised exchange marketplaces

| Exchange     | Currencies              |
| ------------ | ----------------------- |
| Poloniex     | BTC                     |
| Kraken       | BTC, USD, EUR, CAD, GBP |
| Gatecoin     | BTC, EUR                |
| Bitfinex     | BTC, USD                |
| Bittrex      | BTC                     |
| Bluetrade    | BTC, LTC, DOGE          |
| HitBTC       | BTC                     |
| Livecoin     | BTC                     |
| Coinsquare   | BTC                     |
| Bittylicious | GBP                     |
| BTER         | CNY                     |
| Yunbi        | CNY                     |
| Metaexchange | BTC                     |

You can also search for "{insert your country} Ether exchange".

There's also this:
<https://myetherwallet.github.io/knowledge-base/faq/buying-selling-exchanging-eth-tokens-fiat.html>.
For further info (which lists more exchanges), see
[here](Getting-Ether:-further-info).

<!-- TODO: Fix link above -->

## Centralised fixed rate exchanges

| Exchange                     | Currencies                     |
| ---------------------------- | ------------------------------ |
| [Shapeshift](https://shapeshift.io)  | BTC, LTC, DOGE, Other          |
| [Karsha](https://karsha.biz) | 75+ Crypto/ERC20, 3 Fiat (USD) |
| [Bity](https://bity.com)     | BTC, USD, EUR, CHF             |

## Trading and price analytics

-   [ETH markets exhaustive listing by volume on
    coinmarketcap](https://coinmarketcap.com/currencies/ethereum/#markets)
-   Aggregating realtime stats of major ETH markets:
    -   [Tradeblock](https://tradeblock.com/ethereum)
    -   [EthereumWisdom](http://ethereumwisdom.com)
    -   [Cryptocompare](https://www.cryptocompare.com/coins/eth/overview)
    -   [Coinmarketcap](https://coinmarketcap.com/currencies/ethereum/)
-   [EthGasStation](https://ethgasstation.info) is useful for checking
    the gas price to set before making a transaction lists, as well as
    checking [Gas Guzzlers, or the 'Top 10 ETH Contracts By Transaction
    Count Over the Last 1,500
    Blocks'](https://ethgasstation.info/gasguzzlers.php)

## Online wallets, paper wallets, and cold storage

<!-- TODO: This is here just a dumping ground of links and notes Please move this over in a listing form to ecosystem. Keep examples here, maybe explain paranoid practices, list dangers -->

### Kryptokit Jaxx

-   [Jaxx main site](http://jaxx.io/)
-   [Mobile release](http://favs.pw/first-ethereum-mobile-app-released/#.VsHn_PGPL5c)

### Etherwall

-   [Etherwall website](http://www.etherwall.com/)
-   [Etherwall source](https://github.com/almindor/etherwall)

### MyEtherWallet

-   [MyEtherWallet website](https://www.myetherwallet.com/)
-   [MyEtherWallet
    source](https://github.com/kvhnuke/etherwallet/)
-   [Chrome
    extension](http://sebfor.com/myetherwallet-chrome-extension-release/)

### Cold storage

-   [Icebox](https://github.com/ConsenSys/icebox) by
    [ConsenSys](https://consensys.net/) - Cold storage based on
    lightwallet with HD wallet library integrated.
-   [Reddit discussion
    1](https://www.reddit.com/r/ethereum/comments/45uvmy/offline_cold_storage_question/offline_cold_storage_question)
-   [How to setup a cold storage
    wallet](https://www.reddit.com/r/ethereum/comments/48wfbv/eli5_how_to_setup_a_cold_storage_wallet_as/)

### Hardware wallet

-   [reddit discussion
    2](https://www.reddit.com/r/ethereum/comments/45siaq/hardware_wallet/)
-   [reddit discussion
    3](https://www.reddit.com/r/ethereum/comments/4521o4/crowdfunding_ethereum_hardware_cold_storage_wallet/)

### Misc

-   [Kraken Wallet Sweeper Tool](https://www.kraken.com/ether) -
    Pre-sale wallet import
-   [Recommended ways to safely store
    ether](http://ethereum.stackexchange.com/questions/1239/what-is-the-recommended-way-to-safely-store-ether)
-   [How to buy and store
    ether](http://sebfor.com/how-to-buy-and-store-ether/)
-   [A laymen\\'s intro into brute forcing and why not to use
    brain
    wallets](http://www.fastcompany.com/3056651/researchers-find-a-crack-that-drains-supposedly-secure-bitcoin-wallets)
-   [Pyethsaletool](https://github.com/ethereum/pyethsaletool/blob/master/README.md)
-   [Account vs
    wallet](https://www.reddit.com/r/ethereum/comments/47j3r5/eli5_accounts_vs_wallet_contracts_on_mist/)

## Further discussion
> Largely migrated content, needs editing and consolidation
{.is-warning}

Summary: compare deals with buying and sell through different exchanges such as P2P ones with an arbitrator like [**LocalEthereum**](https://localethereum.com), or with centralized exchanges (which vary with your local jurisdiction, e.g. in Australia there is [BTCmarkets](https://btcmarkets.net/fees) and in the US plus worldwide there is [Coinbase](https://www.coinbase.com), which also allows you to spend cryptocurrencies e.g. with a debit card. For more see the table below, [here](https://github.com/jamesray1/Ethereum-introduction/wiki/Ethereum-introduction#table-of-exchanges)).

The simplest way may be to use [**LocalEthereum**](https://localethereum.com), where you don't need to go through KYC processes. The creator of this wiki has found that "I can **sell Ether for a better deal** than I can find with an exchange, without any trading or withdrawal fees, apart from those associated with different payment methods". I like that it has lower fees compared to exchanges. I also read about how the localethereum platform works, and it seems pretty secure. The maker fee (which is what the party of the trade that puts up the offer) is 0.25% while the taker fee is 0.75%. [BTCmarkets](https://btcmarkets.net/fees) has higher fees compared to the maker fee, and higher than the taker fee if the amount is below $3000. Additionally, there have been hacks with exchanges like Mt. Gox and Bithumb. That's harder to achieve with localethereum since they can't get access to your funds, they can only settle disputes (if they arise) by sending the funds in the escrow to the buyer or the seller. However, I have been able to find a **better deal**, at least at certain times, with buying Ether if I buy through [**BTCmarkets**](https://btcmarkets.net/fees), although that would be slower via BPAY with bank transfer than paying via cash deposit via an ATM or bank."

More information about Ether is [here](http://ethdocs.org/en/latest/ether.html).

Disclaimer from the creator of this wiki: I have put most of my funds in Ether, the currency of Ethereum. Does that shock you? 😲 Yep, it's risky, but I've done due diligence 🔍 with fundamental analysis, and a little bit of sentiment and technical analysis, and I think that the market cap of Ether will continue to grow 🌱🌳 and increase, albeit with some volatility 📈. I consider it a digital currency that is in a pioneering, rapid growth stage of development (fuelled by a lot of genuine uptake of the currency as well as speculation about its future value, if not its current value), not just an asset. I hope my post will outline why investing in Ether is a good idea (and not just investing a small percentage of your cash, unless you are tied up with a mortgage 🏠 or have other monetary or non-monetary ties or circumstances that limit your investable capital). However, if you don't want to risk the downside volatility, e.g. if you don't have any risk capital, then you may want to consider buying a stable coin like [Dai Coin](https://makerdao.com/) instead.

Based on my research below, <strong>if you're in Australia</strong> 🇦🇺 (otherwise skip to the next paragraph), I recommend creating an account with BTCmarkets.net, verifying your ID, and using BPAY or PoliPayments to deposit AUD. Note that the rest of the following info in this paragraph is outdated since MEBank used to not support BPAY publicly, but now they do. If your bank doesn't support PoliPayments and you want to use that instead of BPAY, although I can't think of any good reason why you'd want to use PoliPayments over BPAY, then you can set up a bank account with BOQ (or <a href="https://www.polipayments.com/Banks" target="_blank" rel="noopener">any other bank that supports POLi Payments</a>, <a href="https://www.marketforces.org.au/banks/compare" target="_blank" rel="noopener">doesn't invest in fossil fuels</a> and <a href="https://www.choice.com.au/money/banking/savings-options/articles/top-fee-free-bank-accounts" target="_blank" rel="noopener">has no fees for transaction and savings accounts</a> [note that Bendigo doesn't have an Ultimate Everyday account any more]. You can probably ignore the interest rate since it is so marginal compared to other bank's rates and the gains that you are likely to make by holding funds with Ether instead. However, when I did research for interest rates I found that ME Bank savings rates were second only to UBank, which invests in fossil fuels indirectly as it is owned by NAB.

## Table of exchanges

You can use [localethereum](https://localethereum.com) anywhere, but in my experience you may not get as good a deal as buying it on a local exchange.

<strong>If you're not in Australia 🇦🇺</strong>, then here's a comparison of exchange rates 💱 for fiat to crypto- and crypto- to crypto- currencies (note that there is still a focus on Australia, but you can click on the links to get more information of the fees):
<table border="1" width="643" cellspacing="0" cellpadding="4"><colgroup> <col width="314" /> <col width="311" /> </colgroup>
<tbody>
<tr valign="TOP">
<td width="314"> Exchange link (may go to a fees page)</td>
<td width="311">Fiat to crypto exchange fee buy/sell spread</td>
</tr>
<tr valign="TOP">
<td width="314" height="10"><a href="https://btcmarkets.net/fees" target="_blank" rel="noopener">BTCmarkets</a></td>
<td width="311">AUD is the only fiat currency. 0.85% trading fee. Funds available to deposit, withdraw, buy and sell are: AUD, ETH, ETC, BTC and LTC. To deposit AUD, you need to verify your account and then use POLi Payments (available banks are <a href="https://www.polipayments.com/Banks" target="_blank" rel="noopener">here</a>. My bank is ME Bank, which doesn't support POLi Payments. I applied with BOQ because they do support POLi Payments, they <a href="https://www.marketforces.org.au/banks/compare" target="_blank" rel="noopener">don't invest in fossil fuels</a> [like ME Bank] and they have <a href="http://www.boq.com.au/day2day.htm" target="_blank" rel="noopener">transaction and savings accounts with no fees</a> [like ME Bank].)</td>
</tr>
<tr valign="TOP">
<td width="314" height="10"><a href="http://gdax.com/fees/" target="_blank" rel="noopener">GDAX</a></td>
<td width="311">0.25/.3% maker fee low volume, 0% taker fee BTC for USD/EUR/GBP, ETH/LTC for USD/BTC/EUR</td>
</tr>
<tr valign="TOP">
<td width="314" height="10"><a href="https://www.coinjar.com.au/">Coinjar</a>, has a debit card with accounts for Ether, BTC, XRP and LTC.</td>
<td width="311">1.00% AUD/BTC (and only AUD/BTC)</td>
</tr>
<tr valign="TOP">
<td width="314" height="10"><a href="https://support.coinbase.com/customer/en/portal/articles/2109597">Coinbase</a></td>
<td width="311">In Aus: 3.99% credit/debit card only (no other transaction method accepted). Other fiat and crypto currencies are available.</td>
</tr>
<tr valign="TOP">
<td width="314"><a href="https://cex.io/" target="_blank" rel="noopener">CEX</a></td>
<td width="311">7% BTC/ETH for USD/EUR/GBP/RUB</td>
</tr>
<tr valign="TOP">
<td width="314"><a href="https://ice3x.com/" target="_blank" rel="noopener">ice3x</a></td>
<td width="311">1% ZAR/BTC</td>
</tr>
<tr valign="TOP">
<td width="314"><a href="https://www.luno.com/trade/XBTZAR" target="_blank" rel="noopener">Luno</a></td>
<td width="311">ZAR/BTC fee not easy to find</td>
</tr>
<tr valign="TOP">
<td width="314"><a href="https://www.okcoin.cn/" target="_blank" rel="noopener">okcoin</a></td>
<td width="311">CNY/USD for BTC/LTC, fee not easy to find</td>
</tr>
<tr valign="TOP">
<td width="314"><a href="https://www.maicoin.com/">Maicoin</a></td>
<td width="311">TN/BTC Fee not shown, claimed none</td>
</tr>
</tbody>
</table>
<table border="1" width="100%" cellspacing="0" cellpadding="4"><colgroup> <col width="128*" /> <col width="128*" /> </colgroup>
<tbody>
<tr valign="TOP">
<td width="50%"></td>
<td width="50%">Crypto to crypto exchange fee / buy/sell spread</td>
</tr>
<tr valign="TOP">
<td width="50%" height="21"><a href="https://poloniex.com/">Poloniex</a></td>
<td width="50%">0.15/.25% BTC/ETH “maker-taker” (presumably the same as buy-sell)</td>
</tr>
<tr valign="TOP">
<td width="50%"><a href="http://gdax.com/fees/">gdax.com/fees/</a></td>
<td width="50%">0.25/.3% maker fee low volume, 0% taker fee ETH/LTC for BTC</td>
</tr>
<tr valign="TOP">
<td width="50%"><a href="https://www.exodus.io/">Exodus</a></td>
<td width="50%">~0.4720–.528% BTC/ETH variable. Desktop app. Sometimes currencies are not available for exchange!</td>
</tr>
<tr valign="TOP">
<td width="50%"><a href="https://nvo.io/">NVO</a></td>
<td width="50%">Decentralised. ICO 05/27/17 02:00 UTC to 06/27/17 02:00 UTC</td>
</tr>
</tbody>
</table>

Exchanges are listed in [this article](https://medium.com/@Ethereum_AI/ethereum-introduction-what-exactly-is-it-why-care-how-to-invest-9a627ab04408), which I've copied and pasted (repetition is OK):

**America, US dollars**

https://www.coinbase.com

https://gemini.com/

**Australian Dollar**

https://btcmarkets.net/

**Canadian Dollar**

https://www.quadrigacx.com

**Chinese Yuan**

https://www.huobi.com

https://www.okcoin.com

https://yunbi.com

**European Euros**

https://www.kraken.com

**India**

https://duckduckgo.com/?q=Ethereum+exchange+india&t=brave&ia=web

**Mexican Peso**

https://bitso.com

**South Korean Won**

https://coinone.co.kr/

https://www.bithumb.com/

## More details about what James Ray tried (not very necessary to know)

You could skip to the [next section](https://github.com/ethereum/wiki/wiki/Ethereum-introduction.md#development)

I bought BTC in a different way. Step 2 worked for me. I will try step 1 next time I buy more BTC.

I created an account on btcmarkets.net, verified my email address, tried to login, but couldn't. I tried to disable two factor authentication, but it asked for my mobile number, which I didn't enter when I created my account. I tried to reset my password and log in again, but that didn't work. I entered my email address correctly. I sent a message to support to ask for help. I figured out that my **password was too long**, and have notified btcmarkets.net. After creating a password of 23 characters, I was able to log in. I created another password of 56 characters using Chinese characters, emojis and ASCII characters, and was able to log in. (Incidentally, it is a hassle to do this, so a decentralised, private password generator would be wonderful.)

**Don't do this (buy BTC then convert it to ETH), skip**: The following steps are what I have tried so far, in detail.
<ol>
	<li>Convert AUD to Bitcoin (BTC) via an exchange like <a href="https://www.coinjar.com/" target="_blank" rel="nofollow noopener noreferrer">Coinjar</a>. I left a review of Coinjar <a href="https://au.trustpilot.com/reviews/59391a3d20b79f0b9c73a629" target="_blank" rel="noopener">here</a>. Fee: 1%. While this step is tailored for Australia, it can be adapted to any country that has a bitcoin exchange.</li>
	<li>I created a <a href="https://poloniex.com/" target="_blank" rel="noopener">Poloniex</a> account, sent funds from got the Bitcoin deposit address, then sent my BitGo funds to that address. Once the transaction completed, I then used Poloniex Exchange to convert to Eth, with a maker-taker fee of: <a class="standard" href="https://poloniex.com/feeTier"><span class="makerFee">0.15</span>/<span class="takerFee">0.25</span>%</a>.</li>
</ol>
Before step 2 above, I tried the following:
1. **Outdated**: ~~Create an Ethereum Wallet 👛 like <a href="https://www.myetherwallet.com/" target="_blank" rel="nofollow noopener noreferrer">MyEtherWallet</a>. Unfortunately <a href="https://github.com/ethereum/mist" target="_blank" rel="noopener">Mist</a>, a program being developed by Ethereum that has a browser and a wallet is <a href="https://github.com/ethereum/mist/releases" target="_blank" rel="noopener">still a pre-release</a>, so it may not be very suitable for end users just yet.~~
2. Convert BTC to Ether (ETH) via a cryptocurrency exchange like <a href="https://shapeshift.io/" target="_blank" rel="nofollow noopener noreferrer">Shapeshift</a>. Use a precise transaction, make sure the amount is within the min. and max. deposit. Copy and paste the bitcoin address in Coinjar by signing in (if you aren't already) and going to Accounts > Everyday Bitcoin > View address. Put this address as the refundable address. Copy and paste the address from <a href="https://www.myetherwallet.com/" target="_blank" rel="nofollow noopener noreferrer">MyEtherWallet</a>. Put this as the destination address. Tick the box to save the destination address for future payments. However, **this didn't work**.

~~I also sent an email to Coinjar to suggest that they develop functionality for purchasing Ether directly using AUD. You can do the same with the exchange of your choice.~~ Implemented

~~I have been able to deposit funds into Coinjar (needing to be less than the transaction limits) but have not been able to get Eth funds as of yet.~~ I have also tried to create an account on BitGo, send coins from Coinjar to BitGo, and use Shapeshift with that account and still with MyEtherWallet, **however that didn't work**.

I will not discuss trading (which I mean buying with the intention to sell most or all of the purchase at any future time particularly in the short term in order to realize a profit) as I am not very interested in trying to guess the short-term direction of markets (although I admit that trading helps to provide liquidity), plus it is very difficult to predict the short-term direction of the price. However, I recommend that you set up alerts with [Coinwink](https://coinwink.com/), but bear in mind that if you hold it for the long-term, the price should continue to go up, so if there is a short-term correction, you could bear it through until you make a profit. Finally, it cannot be overemphasised that it is important to actually use the currency, so consider doing that, look into dapps that you'd actually use, and use them, and sign up for updates or check in from time to time for ones that are under development.