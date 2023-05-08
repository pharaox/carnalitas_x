# Changelog

## Version 0.8.0

### Interactions

* Ensured that piety is appropriately lost also when buying, seizing, or gifting a slave if slavery is not accepted according to doctrines.
* The impact of religious doctrines on *Free Slave* and *Ransom Slave* is no longer reduced compared to other interactions.

### Events

* Added *Runaway Slave* event (`carnx_slave.0003`). One of your slaves flees, taking some of your valuables with them, and a knight is chosen as a scapegoat.
* Added *Freedom for a Slave* event (`carnx_slave.0005`). Your Court Chaplain demands the freedom of one of your slaves because your faith does not permit owning slaves of their faith.
* Added *Piety Loss From Slaves* event (`carnx_slave.0004`). Once a year rulers may lose piety for any slaves owned against religious doctrines.

## Version 0.7.0

### Interactions

* Ensured that only non-busy count or above rulers can start slave interactions
* Nerfed impact of strong hooks (+100 instead of auto accept)
* All rulers from neighboring realms are now regarded as valid buyers or sellers
* Changed AI greed slave price multipliers to correspond to player slave price multipliers
* Slave prices are now rounded normally instead of down

### Game Rules

* Added *Valid Buyers or Sellers* game rule to specify which rules are considered valid buyers or sellers
* Added *Number of Potential Buyers* game rule to limit the max number of buyers shown in the *Sell Slaves* interaction

### Bug Fixes

* Ensured that rulers that can't have councillors, court positions, knights, or commanders don't consider slaves for such roles
* Fixed the tribal price multiplier to ensure that the two parties are always different characters

### Housekeeping

* Refactored character interactions and triggers to correspond to *Search & Trade Artifacts*

## Version 0.6.0

### Court Positions

* Added 1 new court position that is reserved for slaves or former slaves:
  * *Slave Eunuch*: stewardship / intrigue, restricted to polygamous religions and cultures and cultures that can appoint *Chief Eunuch*, gives court grandeur, development growth, and hostile scheme resistance (3 positions)
* Children of *Slave Concubines* are no longer slaves and have their correct father, house, dynasty, faith, and culture, including effects of dynasty perks.
  * If the concubine is the mother, the father is the mother's liege, and they get his house, dynasty, faith, and culture.
  * If the concubine is the father, the father is the real father, and they get their mother's house, dynasty, faith, and culture.

### Events

* AI rulers may have sex with one of their slaves (or former slaves that are also *Slave Concubines*) once a year if they are attracted to them.
  * This applies also to the human player if the *Make Love* interaction is disabled.
  * The chance of pregnancy is for the moment hardcoded at 10%.

### Bug Fixes

* Former slaves that are married are no longer eligible to become *Slave Concubines*.
* It is now possible to *Make Love* to a former slave that is also a *Slave Concubine*.

## Version 0.5.0

### Miscellaneous

* Characters that can be enslaved and have a base price higher than a threshold are now captured instead of killed during raids and sieges.
* Characters captured during a raid have 50% chance of getting the "marked for enslavement" modifier, which makes enslavement by the AI more likely.
* It is now possible to buy and sell slaves from / to foreign rulers within a dynamic trading range depending on rank, measured as the distance between capitals.
* AI rulers will attempt to precision target one ruler per slave within the above range when selling slaves.
* AI rulers will attempt to precision target one ruler per slave when ransoming slaves.

### Bug Fixes

* Traits and perks of the army commander are now properly checked when determining the chance to capture prisoners during a raid (vanilla bug).
* Fixed impact of age on slave prices and interactions.

### Housekeeping

* Extracted values related to age for easier overriding by compatibility submods.

## Version 0.4.0

### Court Positions

* Added 2 new court positions that are reserved for slaves or former slaves conferring somewhat lesser but still tangible advantages:
  * *Slave Concubine*: diplomacy / attraction, restricted to polygamous religions and cultures, gives court grandeur and prestige (5 positions)
  * *Mameluke Captain*: martial / prowess, restricted to clan governments, gives court grandeur and knights effectiveness (3 positions)
* Made the following 14 court positions allowed to slaves: *Court Physician*, *Antiquarian*, *Court Gardener*, *Court Tutor*, *Food Taster*, *Seneschal*, *Cupbearer* (if tribal or clan government), *Chief Eunuch*, *Court Jester*, *Court Poet*, *Court Musician*, *Bodyguard*, *Personal Champion*, *Executioner*
* Made the rest of the court positions forbidden to slaves. These court positions are considered ceremonial or religious, or are restricted due to game limitations.
* Made the following 4 council positions allowed to slaves: *Chancellor* (if tribal or clan government), *Steward* (if tribal or clan government), *Marshal* (if tribal or clan government, *Spymaster*
* Made the *Court Chaplain* council position forbidden to slaves, since it is considered religious.
* Reduced salaries of court positions if held by slaves (to 25% of the original value).
* Increased opinion gain of slaves appointed to council and court positions to (3x compared to other courtiers).
* Ensured AI rulers are more likely to appoint slaves to court positions.
* Logged debug messages on all council and court positions received and revoked by slaves.

### Interactions

* Made the AI take into account their fitness for all allowed court positions when evaluating slaves.
* Ensured the AI takes into account only the court position with the max aptitude difference and the council position with the max skill difference when evaluating slaves.
* Added more court position traits to influence the slave base price.

### Events

* Changed the *Buy Foreign Slaves* event to generate "valuable options" that are a good fit for particular positions, instead of "good" in general.
* Added character templates for the 2 new court positions, as well as an eunuch template. These are used by the *Buy Foreign Slaves* event.

### Miscellaneous

* Increased the percentage of slaves that are enslaved when imprisoned vs. generated by the *Buy Foreign Slaves* event (from 28% to 41%).
* Increased the percentage of imprisonments that lead to enslavement (from 12% to 18%).
* Ensured debug messages are logged only in debug mode.
* Added compatibility submods for EK2 and Tales of Ireland.

### Housekeeping

* Removed references to vanilla religions, heritages, doctrines, etc. as much as possible.
* Extracted values, triggers, and effects to be overridden by compatibility submods.

## Version 0.3.0

### Interactions

#### General

* Improved all interaction effects to show more relevant information in interface messages.
* Added "age considerations" AI modifier to all slave interactions. The AI is now more willing to buy / acquire and less willing to sell / release slaves if they are between 6 and 50 years of age, and vice versa if they are not. The modifier peaks between 16 and 30 years of age. It is only applied if the slave is considered "useful" to the AI.
* Added additional reasons to the AI to consider slaves as useful when buying / acquiring:
  * Lacking a good court chaplain (based on learning).
  * Lacking a good court physician or antiquarian (based on aptitude; court physician was there also before but it was broken).
  * Could use a good commander (based on martial and commander traits).
* Nerfed the "visibly fertile female" AI modifier to slave interactions.
* Nerfed the attraction AI modifier to slave interactions.
* Buffed the AI unwillingness to sell / release court positions.

#### Gifting Slaves

* Added new *Gift Slave* interaction (`carnx_gift_slave_interaction`). Gift a slave to another ruler for an opinion gain. The opinion gain is proportional to the slave base price and to the "gift opinion / gift value" ratio of the *Send Gift* vanilla interaction. AI rulers are much more likely to accept slaves as gifts than to buy them.

#### Buying ans Selling Slaves

* Changed *Buy Slaves* and *Sell Slaves* to redirect to *Buy Slave* and *Sell Slave* for the actual trade in order to show the AI acceptance reasons and prevent exploits.
* Changed *Sell Slaves* to show only slaves that can actually be sold to somebody.
* Ensured the AI replies immediately to *Buy Slave* and *Sell Slave* offers.
* Enabled the use of hooks in *Buy Slave* and *Sell Slave* interactions.
* Added "price considerations" AI modifier to *Buy Slave* and *Sell Slave* interactions. When buying, the AI is now more willing to buy slaves that are cheap (price < `minor_gold_value`) and less willing to buy slaves that are expensive (price > `major_gold_value`), and vice versa when selling.
* Ensured the AI pays no more than their `short_term_gold` for slaves and changed the corresponding descriptions accordingly.
* Changed the description of the AI base reluctance to spend money modifier from "cannot afford the gold" to "is reluctant to spend gold".

#### Ransoming Slaves

* Buffed dread impact on *Ransom Slave* AI willingness for vassals and below. They will now practically always accept if intimidated or cowed.
* Buffed the AI base willingness to offer *Ransom Slave* to other rulers.
* Added "ransomed" memory as a different memory from "freed".

#### Slave Prices

* Reduced the correction multiplier of the slave base price from 0.75 to 0.6, making slaves cheaper across the board.
* Adjusted slave prices down for tribal rulers (as everything is cheaper for them).
* Changed some factors affecting the slave base price:
  * Nerfed claims to 100 for any type of claim (before it scaled from 100 to 250).
  * Rebalanced court physician traits to match aptitude, added an antiquarian trait.
  * Nerfed prowess from 5 to 3 per point.
  * Buffed attraction (from 20 to 30 for max attraction).
  * Nerfed "visibly fertile female" from 20 to 15.
  * Added age (up to 12, similar to the AI modifier described above).

### Bug Fixes

* Fixed *Buy Slaves* and *Sell Slaves* allowing to select a slave after a buyer or a seller has been selected.
* Fixed *Ransom Slave* not selecting a default option and allowing to be sent without an option selected.
* Fixed concubines not being "divorced" when enslaved (Carnalitas bug).

### Miscellaneous

* If a character loses their last title, their slaves are no longer freed, instead they are seized by the new title holder.
* Enabled imprisoning slaves w/o tyranny (vanilla change).

### Housekeeping

* Extracted commonly checked conditions as scripted triggers triggers in `carnx_slave_triggers.txt`.
* Extracted positive and negative "impact values" as script values in `carnx_basic_values.txt`.
* Extracted *Seize Slave* effects as scripted effects in `carnx_slave_effects.txt`.
* Refactored all effects into "interaction" and "actual" effects.

## Version 0.2.0

### Interactions

* Multiplied the slave base price (`carnx_slave_base_price_value`) by a correction multiplier, currently 0.75.

### Bug Fixes

* Ensured *Buy Foreign Slaves* event (`carnx_slave.0001`) is not fired if slavery is disabled.

### Miscellaneous

* Verified compatibility with *Carnalitas Slavery Expansion*.
* Updated `README.md` with additional information regarding compatibility with other mods and Carnalitas game rules.

## Version 0.1.0

### Interactions

* Modified *Buy Slave* interaction (`carn_buy_slave_directly_interaction`). Buy a slave from another ruler. If accepted, the slave is bought at the seller's price (`carnx_slave_ask_price_value`).
* Modified *Sell Slave* interaction (`carn_sell_slave_interaction`). Sell one of your slaves to another ruler. If accepted, the slave is sold at the buyers's price (`carnx_slave_bid_price_value`).
* Modified *Enslave* interaction (`carn_enslave_interaction`). Enslave one of your prisoners.
* Modified *Free Slave* interaction (`carn_free_slave_interaction`). Free one of your slaves, potentially asking for gold, conversion, renouncing of claims, or a favor. If asked for gold and accepted, the slave pays their ransom cost (`carnx_slave_ransom_cost_value`).
* Modified *Seize Slave* interaction (`carn_seize_slave_interaction`). Seize somebody else's slave that is your prisoner.
* Added *Buy Slaves* interaction (`carnx_buy_slaves_interaction`). Buy slaves from other rulers that are willing to sell them to you. This is a convenience interaction for the human player to quickly find all slaves they could buy and the prices at which they could be bought. Slaves are bought at the seller's price (`carnx_slave_ask_price_value`).
* Added *Sell Slaves* interaction (`carnx_sell_slaves_interaction`). Sell some of your slaves to other rulers willing to buy them from you. This is a convenience interaction for the human player to quickly find all potential buyers for their slaves and the prices at which they could be sold. Slaves are sold at the buyers's price (`carnx_slave_bid_price_value`)
* Added *Ransom Slave* interaction (`carnx_ransom_slave_interaction`). Ransom one of your slaves with another ruler that is their relative or relation for either gold or a favor. If asked for gold and accepted, the payer pays the slave's ransom cost (`carnx_slave_ransom_cost_value`).
* Rebalanced religious doctrine impact on all slavery interactions.

### Events

* Added *Buy Foreign Slaves* event (`carnx_slave.0001`). Slave traders bring two slaves for sale and you can buy one of them.

### Bug Fixes

* Fixed slaves wandering off if a slave owner dies and their heir doesn't inherit their court (e.g. because they have their own court). Such slaves are now instead added to the court of their new owner.
* Fixed characters continuing to own slaves after they stop being a ruler. Slaves of such characters are now freed automatically.

### Miscellaneous

* Added slave character memories.
* Rebalanced dread, tyranny, piety, and stress gain or loss from enslaving and freeing slaves.
* Reduced frequency of slave conversions by the AI by overriding `ask_for_conversion_courtier_interaction` from the base game.
* Added `carnx_capture_potential_slaves_effect` for use in other mods

### Housekeeping

* Extracted basic values and triggers into separate files.
* Added `README.md`, `LICENSE.md`, `CHANGELOG.md`, and `VERSION` files.
