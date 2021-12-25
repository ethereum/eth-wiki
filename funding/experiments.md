---
title: Funding Experiments
description: 
published: true
date: 2019-07-31T15:15:54.268Z
tags: 
---

See the top level [Funding](/funding/funding.md) page for sources of funding and related info.

Please use this [EthMagicians thread for discussion »](https://ethereum-magicians.org/t/funding/funding.md-and-eth1x/3496)

# Resources

* Related to this page, @bmann wrote up a Funding Taxonomy & Issues https://ethereum-magicians.org/t/funding/funding.md-taxonomy-issues-for-ethereum-ecosystem/2014
* Long term cashflow & budgets for projects, with templates by @bmann https://ethereum-magicians.org/t/discussing-long-term-cashflow-and-budgets-for-ethereum-projects-teams-and-individuals/1849

# Funding Required

There are 2 - 3 types of funding required to sustain and grow the Ethereum ecosystem. For purposes of this document, we are focusing on the existing Ethereum (ETH1x) Stack.

_Funding time frame_ is defined as **maximum** time from application to money-in-bank. Ideally, this process also leads to a "quick no" if not approved -- so that people get feedback and can move on to looking at other opportunities. This could also be mixed and matched -- get started with a one-off grant, and in parallel work on an R&D or Infrastructure sized grant. People idling for 3 months is not an ideal situation, and in many cases is only possible if they already have a day job, are part of a company, or otherwise are burning savings. 

See the **Compensation** section for the background on person month costs.

Project time is start to finish.

## Projects

One-off grants to seed apps, experiments, and composable pieces of code.

* Funding time frame: 1 month
* Amount: < $50K (5 person months)
* Project time: 3 months


## R&D

Foundational problem solving, new standard creation, major apps or components to be used throughout the ecosystem.

* Funding time frame: 2 months
* Amount: $60K - $120K (6 - 12 person months)
* Project time: 3 - 6 months

One or two senior people working for 3 - 6 months. This might produce one major feature or EIP.

## Infrastructure and Maintenance

Dedicated maintainer funding to work on an app or area of focus (e.g. testing).

* Funding time frame: 3 months
* Amount: $120K+ (12+ person months)
* Project time: 12 months

Typically would need 1 - 2 senior people plus collaboration across multiple ecosystem groups and/or 1-2 additional team members or sub-projects.

Example: Testing & Hardfork Rollout Process.

# Compensation

The current approach by the EF is that they pay contractors a max of $50/hr. For full time, 160 hours per month, that works out to $8K/month, or $96K annual "salary". As well, EF covers some expenses and travel.

We use $10KUSD per month per "senior" person as a baseline compensation. Teams can still slice and dice this how they like, but it simplifies budgeting while still putting the onus on the team to cover travel, taxes, and other expenses.

Rather than having every team figure out what they can afford to work for, we use a flat rate approach.

For contract work, this is vastly underpaying ($100 - $300USD/hour for senior people). But the approach should be that you're "breaking even" while doing a tour of duty working on core, open source infrastructure. For "annual salary", this is a little on the low side (people in the Bay Area would say VERY low), but I think it's a decent starting point. Can any organization -- the EF or otherwise -- retain people at those rates? No, probably not -- so you need to think about retention and/or training up juniors and bringing in new people over time. Right now very little of this is happening.

And, should go without saying: if per project or R&D work isn't longer term, and people take a couple of months before more funding is approved, then their effective compensation is much lower (which is one of the reasons that contractors bill a higher hourly rate).

# What needs funding in ETH1x?

The [ETH1 page](/eth1/eth1.md) lists Working Groups, which came out of [CoreDevsBerlin](/eth1/coredevsberlin.md). Alexey's State Rent group is sort of "perma funded" by the EF for now, and Alexey negotiated 3 months of funding for some of the other Working Groups.

Infrastructure, using Testing as an example, is largely leaderless. There are a couple of people paid by the EF that work on it. Hasn't been an effort to coordinate testnets, consensus tests, network tests, etc. White Block / Zak Cole have said they could lead some of this.

Coordination (eg. release management) doesn't have a solid process and no one dedicated to it other than Hudson (who also is the only community person, travels a ton, AND does devops work for the foundation). Danno & Tim Beiko who work for Pegasys / ConsenSys deserve a shout out for leaning into the hard fork process and EIP / All Core Devs process. Alex (axic) is also doing a ton of work around this, but is also juggling EVM work and eWASM work and a ton of other development projects.

Infrastructure for ETH1x broadly is kind of run by various people who work with the EF, but is also largely undocumented and not currently able to be run by anyone outside the EF. There is an attempt at documenting what infrastructure is needed / who has keys to what on the [Infrastructure](/governance/infrastructure.md) page.

I think it would be a very interesting process to see how many people are working on ETH1x across the EF, Parity, and Pegasys (just listing those that have active mainnet clients -- see [ETH1 clients](/eth1/clients.md)).

Infrastructure is this special case which is most effective when done "centrally" or at least collaborated on closely.

Only Goerli Testnet is an example of an independent team / group coming together to do this effectively.

## Detailed Budgets

Since this has come up several times, I don't think this is necessary. It's all just people, and you can use the Compensation section above to just see how many people you need for how long.

So, for example, let's say there was a Testing lead plus 1 more full time person, in addition to people already at the EF and some volunteers from White Block and Pegasys. They'd work on improving and documenting testing, hard fork process, testnets, and so on, for 1 year. 2 people @ $10KUSD x 12 months = $240K. On top of that, you might fund R&D or Projects of another $60K, where those 2 people would help coordinate and guide those projects.

Those people are separately responsible for software, hardware, travel, taxes in their home country, accounting, and who knows what else. The budget templates linked at the top of this page have a pretty easy way to outline this, but the main cost driver is going to be how many person months need to get funded.

In case that's confusing, the Projects section says < $50K grants. So, it might be 4 person months, of 2 people for 2 months and then some contract work.