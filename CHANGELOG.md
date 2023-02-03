# Version 0.2.0

## Interactions

* Multiplied the slave base price (`carnx_slave_base_price_value`) by a correction multiplier, currently 0.75.

## Bug Fixes

* Ensured *Buy Foreign Slaves* event (`carnx_slave.0001`) is not fired if slavery is disabled.

## Miscellaneous

* Verified compatibility with *Carnalitas Slavery Expansion*.
* Updated `README.md` with additional information regarding compatibility with other mods and Carnalitas game rules.

# Version 0.1.0

## Interactions

* Modified *Buy Slave* interaction (`carn_buy_slave_directly_interaction`). Buy a slave from another ruler. If accepted, the slave is bought at the seller's price (`carnx_slave_ask_price_value`).
* Modified *Sell Slave* interaction (`carn_sell_slave_interaction`). Sell one of your slaves to another ruler. If accepted, the slave is sold at the buyers's price (`carnx_slave_bid_price_value`).
* Modified *Enslave* interaction (`carn_enslave_interaction`). Enslave one of your prisoners.
* Modified *Free Slave* interaction (`carn_free_slave_interaction`). Free one of your slaves, potentially asking for gold, conversion, renouncing of claims, or a favor. If asked for gold and accepted, the slave pays their ransom cost (`carnx_slave_ransom_cost_value`).
* Modified *Seize Slave* interaction (`carn_seize_slave_interaction`). Seize somebody else's slave that is your prisoner.
* Added *Buy Slaves* interaction (`carnx_buy_slaves_interaction`). Buy slaves from other rulers that are willing to sell them to you. This is a convenience interaction for the human player to quickly find all slaves they could buy and the prices at which they could be bought. Slaves are bought at the seller's price (`carnx_slave_ask_price_value`).
* Added *Sell Slaves* interaction (`carnx_sell_slaves_interaction`). Sell some of your slaves to other rulers willing to buy them from you. This is a convenience interaction for the human player to quickly find all potential buyers for their slaves and the prices at which they could be sold. Slaves are sold at the buyers's price (`carnx_slave_bid_price_value`)
* Added *Ransom Slave* interaction (`carnx_ransom_slave_interaction`). Ransom one of your slaves with another ruler that is their relative or relation for either gold or a favor. If asked for gold and accepted, the payer pays the slave's ransom cost (`carnx_slave_ransom_cost_value`).
* Rebalanced religious doctrine impact on all slavery interactions.

## Events

* Added *Buy Foreign Slaves* event (`carnx_slave.0001`). Slave traders bring two slaves for sale and you can buy one of them.

## Bug Fixes

* Fixed slaves wandering off if a slave owner dies and their heir doesn't inherit their court (e.g. because they have their own court). Such slaves are now instead added to the court of their new owner.
* Fixed characters continuing to own slaves after they stop being a ruler. Slaves of such characters are now freed automatically.

## Miscellaneous

* Added slave character memories.
* Rebalanced dread, tyranny, piety, and stress gain or loss from enslaving and freeing slaves.
* Reduced frequency of slave conversions by the AI by overriding `ask_for_conversion_courtier_interaction` from the base game.
* Added `carnx_capture_potential_slaves_effect` for use in other mods

## Housekeeping

* Extracted basic values and triggers into separate files.
* Added `README.md`, `LICENSE.md`, `CHANGELOG.md`, and `VERSION` files.
