<!-- TITLE: Ethereum 2 -->
<!-- SUBTITLE: Overview of ETH2 related content -->

The best starting point for technical ETH2 info is:
* Specs https://github.com/ethereum/eth2.0-specs
* Project Management https://github.com/ethereum/eth2.0-pm

# FAQ
Frequently Asked Questions about ETH2. Feel free to create a sub-page if your answers are long.

## One-way vs Two-way ETH Bridge for Staking

In the current spec, ETH holders can deposit to the burner contract on the ETH 1.0 chain. This generates a receipt which is used to instantiate the same amount of Ether on the Beacon Chain - a bridge linking the legacy chain to the new one. Community stakeholders have raised concerns that a one-way bridge will lead to price differences between the two chains, derivatives markets and perhaps dissuade validators from joining on the new chain because of the ~1.5 year lockup until Phase 2 of ETH 2.0. While these concerns are not misplaced, it's clear that there are other, more weighty, considerations. This is commentary from Danny Ryan illustrates why a two way bridge is not being included in the Phase 0 spec (quoted verbatim).

"The more we encumber the 1.0 consensus with 2.0, the more we tie the development and fork processes which would likely slow down the shipping/iterating on 2.0. It is not technically infeasible. It would require 2.0 light clients to be run by all 1.0 clients and some changes to the 1.0 consensus rules allowing for a similar burn/receipt method in the opposite direction. If we were to create fungibility, the path would be (1) release 2.0 beacon chain, (2) once stable beacon chain and light clients exist then require 1.0 clients to be light clients of 2.0 and finalize 1.0 with 2.0 and expose beacon chain state root to 1.0 (3) add additional consensus rules to 1.0 and 2.0 to handle the reminting on 1.0 with proof of burn on 2.0.

I think it would be detrimental to 2.0 development to demand fungibility out the gate. Over time as light clients are released and we begin to finalize 1.0 with 2.0 if the community wants fungibility, then we can assess proposals then.

..we can’t prove things about the beacon chain until we force 1.0 clients to agree on the current state of the beacon chain (thus the light client requirement). That’s why it logically falls after finalizing 1.0 if the community really wants it."
