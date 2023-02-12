# Version 0.3.0

## Interactions

* Changed *Buy Slaves* and *Sell Slaves* to redirect to *Buy Slave* and *Sell Slave* for the actual trade in order to show the AI acceptance reasons and prevent exploits.
* Changed *Sell Slaves* to show only slaves that can actually be sold to somebody.
* Improved `carn_buy_slave_effect` to show the slave price and other relevant information properly in messages.
* Enabled the use of hooks in *Buy Slave* and *Sell Slave* interactions.
* Ensured the AI pays no more than their `short_term_gold` for slaves and changed the corresponding descriptions accordingly.
* Added "age considerations" modifier to all slave interactions. The AI is now more willing to buy / acquire and less willing to sell / release slaves if they are between 6 and 50 years of age, and vice versa if they are not. The modifier peaks between 16 and 30 years of age with a peak value of 10. It is only applied if the slave is considered "useful" to the AI.
* Added "price considerations" modifier to *Buy Slave* and *Sell Slave* interactions. When buying, the AI is now more willing to buy slaves that are cheap (price < `minor_gold_value`) and less willing to buy slaves that are expensive (price > `major_gold_value`), and vice versa when selling. The value of the modifier is 10, so it only makes any difference if the AI willingness is on the border. It does not enable selling useless slaves to the AI just because they are cheap, or buying very useful ones just because they are expensive.
* Nerfed the "visibly fertile female" modifier to slave interactions (from 25 to 15).
* Nerfed the attraction modifier to slave interactions (from 50 to 30 for max attraction).
* Nerfed the opinion of actor modifier to *Buy Slave* and *Sell Slave* interactions (from 12 to 10 for max opinion).
* Added additional reasons to the AI to consider slaves as useful when buying / acquiring:
  - Lacking a good court chaplain (based on learning).
  - Lacking a good court physician or antiquarian (based on aptitude; court physician was there also before but it was broken).
  - Could use a good commander (based on martial and commander traits).
* Buffed AI unwillingness to sell / release court positions.
* Reduced the correction multiplier of the slave base price from 0.75 to 0.5, making slaves cheaper across the board.
* Changed some factors affecting the slave base price:
  - Nerfed claims to 100 for any type of claim (before it scaled from 100 to 250).
  - Rebalanced court physician traits to match aptitude, added an antiquarian trait.
  - Nerfed prowess from 5 to 2 per point.
  - Buffed attraction (from 20 to 30 for max attraction).
  - Nerfed "visibly fertile female" from 20 to 15.
  - Added age (up to 10, similar to above).
* Buffed dread impact on *Ransom Slave* AI willingness for vassals and below. They will now practically always accept if intimidated or cowed.
* Buffed AI base willingness to offer *Ransom Slave* to other rulers.
* Ensured the AI replies immediately to *Buy Slave* and *Sell Slave* offers.

## Bug Fixes

* Fixed *Buy Slaves* and *Sell Slaves* allowing to select a slave after a buyer or a seller has been selected.
* Fixed *Ransom Slave* not selecting a default option and allowing to be sent without an option selected.

## Miscellaneous

* If a character loses their last title, their slaves are no longer freed, instead they are seized by the new title holder.
* Enabled imprisoning slaves w/o tyranny (vanilla change).

## Housekeeping

* Extracted commonly checked conditions as scripted triggers triggers in `carnx_slave_triggers.txt`.
* Extracted positive and negative "impact values" as script values in `carnx_basic_values.txt`.
* Extracted *Seize Slave* effects as scripted effects in `carnx_slave_effects.txt`.

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
