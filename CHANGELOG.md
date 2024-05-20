# Changelog

## Version 0.20.1

### Compatibility

* Adapted to CK3 1.12.5.

### Bug Fixes

* Added some missing localization texts and icons.

## Version 0.20.0

### Interactions

* Disabled *Banish*, *Take Vows*, and *Recruit* options of the *Negotiate Release* interaction, as well as the *Take Vows* interaction for slaves.
* Increased piety loss from slavery actions if slavery is considered a crime.
* Added stress impact from slavery actions for *Zealous* and *Cynical* characters.
* Reduced AI willingness to give or accept slaves as gifts due to struggle motives.

### UI

* Added icons for slave court positions.

### Miscellaneous

* Reduced claims impact on slave prices.
* Disabled memories from sex with slaves.

### Performance

* Improved performance of slavery interactions.

### Compatibility

* Added more triggers, effects, and modifiers to be used or overridden in compatibility mods (needed by the AGOT compatibility mod).

### Localization

* Updated Chinese translation (by **@ljingqi**)

## Version 0.19.1

### Compatibility

* Adapted to Carnalitas 2.4.

## Version 0.19.0

### Compatibility

* Adapted to CK3 1.12.2.1 and Carnalitas 2.3.

### Court Positions

* Enabled *Chronicler* court position to be assigned to slaves.

## Version 0.18.0

### Interactions

* Changed impact of slavery doctrines:
  * Slavery being a crime no longer prevents rulers from initiating or accepting slave interactions.
  * Instead, enslaving such characters is penalized by gaining one of the leveled *Slaver* traits, as well as losing a level of fame, while initiating or accepting other interactions is penalized by losing piety.
* Renamed former *Slaver* and *Liberator* traits to *Infamous Slaver* and *Famous Liberator* to avoid confusion with the new *Slaver* traits.
* The *Infamous Slaver* trait is now acquired after enslaving a certain number of people, not after selling people you have enslaved.
* The impact of an action being a crime or shunned on AI willingness is now dynamic depending on AI zeal.

### Miscellaneous

* Players can now always choose all slavery attitudes

### Compatibility

* Added checks if councillors can be actually appointed by their liege when evaluating slaves for councillor positions (needed by the AGOT compatibility mod).
* Added more triggers, effects, and modifiers that can be overridden in compatibility mods (needed by the AGOT compatibility mod).

### Bug Fixes

* Fixed issues with tyranny, opinions, and other consequences of enslaving.
* Eunuchs can no longer impregnate or get Carnalitas body part traits (Carnalitas bug)
* Fixed minor issues in condition checks for councillor and court positions (and made them consistent with Active Courtiers).
* Added commander traits to the slave soldier character template used by the *Buy Foreign Slaves* interaction.

## Version 0.17.2

### Interactions

* Added piety and stress impact for the ransomer in the *Offer Ransom for Slave* and *Demand Ransom for Slave* interactions.

### Game Rules

* Added the *Universe* game rule to enable avoiding errors for historical religions, cultures, and titles with fantasy mods.

### Localization

* Added French translation by **@don-vip**.

## Version 0.17.1

### Compatibility

* Adapted to minor changes in CK3 1.11.2.
* Improved compatibility with *Extended Marriage Doctrines* and *Regula Magistri* mods, based on suggestions from **@OzcarMike**.
  * The *Slave Concubine* court position is now correctly enabled for EMD marriage doctrines.

### Court Positions

* If Carnalitas lactation is enabled, the milk production amount is now taken into account for the *Wet Nurse* court position aptitude.

### Game Rules

* Added the `GG_can_change_rule` flag to all game rules so they could be changed mid-game with the *Gamerule Gadget* mod.

### Localization

* Added Chinese translation by **@Dark_Crow**.
* Updated Russian translation (originally by **@Undertalk**).

### Bug Fixes

* Names for children of Slave Concubines are now appropriate for their updated faith and culture.
* Fixed rare errors in `error.log` reported by **@Eagleman**

## Version 0.17.0

### Compatibility

* Adapted to CK3 1.11.0

### Court Positions

* Enabled *Master Assassin* court position to be assigned to slaves

## Version 0.16.0

### Interactions

* The *Invite to Court* and *Dismiss* vanilla interactions, as well as the *Banish* option of the *Negotiate Release* interaction are no longer available on slaves since they are returned automatically to their owners court.
* The *Demand Payment* vanilla interaction is no longer available on slaves since using it on slaves can be considered an exploit.
* Slaves can now be released from prison without losing dread and without stress impact.
* Freeing a slave using the *Free Slave* interaction no longer releases them from prison if they are imprisoned.
  * Imprisoned slaves can therefore be freed in order to be banished.
* If a slave is released from prison as a result of an interaction is now visible as an interaction effect.
* AI rulers are now much more reluctant to offer hooks as ransom for slaves since this can be exploited via *Demand Payment*.
* *Liberate Slave* now adds "liberated my slave" negative opinion modifier to the former owner, similarly to *Seize Slave*.
* Bought, ransomed, and gifted slaves now travel to their new liege if Travelers (not yet released) is installed.

### Court Positions

* Only slaves, but not former slaves, can now be appointed to slave court positions. If a slave holding a court position is freed, they retain the position, however if it's revoked they can't be appointed to it again.

### Miscellaneous

* Increased the AI reluctance to convert slaves to their faith to avoid freeing them too soon afterwards.
* The pregnancy chance for AI rulers having sex with their slaves is now dynamic if [Carnalitas Love Reimagined](https://www.loverslab.com/files/file/29200-carnalitas-love-reimagined/) is installed.
* Added missing "extra icon" descriptions to slave interactions for hooked characters.

### Bug Fixes

* Fixed the *Demand Ransom for Slaves* and *Offer Ransom for Slaves* convenience interactions sometimes not showing all willing recipients.
* Fixed the *Carnal Court Make Love* interaction not being available for slaves if CBO is installed.

### Housekeeping

* Added a date prefix to debug logs.

## Version 0.15.0

### Compatibility

* Adapted to CK3 1.10.2

### Interactions

* Modified *Demand Manumission* Carnalitas interaction (`carn_free_illegal_slaves_interaction`). Demand the freedom of all illegal slaves from a vassal. It now better reflects the nature of the demand, instead of mostly copying the *Demand Conversion* vanilla interaction.
* Modified *Can Demand Manumission* Carnalitas important action to match the interaction changes.
* Changed *Buy Slave*, *Sell Slave*, and *Gift Slave* interactions to have the standard AI reply time of 4 to 9 days, similarly to *Offer Ransom for Slave* and *Demand Ransom for Slave*.
  * Ensured that a slave can't be sold, ransomed, or gifted multiple times while waiting for a reply.
  * Ensured that the agreed slave price or ransom cost is always paid, even if the buyer or payer short term gold changed meanwhile.
* Changed *Offer Ransom for Slave* and *Demand Ransom for Slave* to allow ransoming for either gold or favor, but not both, similarly to the vanilla *Ransom* interactions. Also similarly to vanilla, it is no longer possible to spend hooks to force ransoming.

### Events

* The *Buy Foreign Slaves* event now involves buying slaves from an actual trader character, instead of simulating a trade via enslaving and removing some gold.
* The *Buy Foreign Slaves* and *Runaway Slave* events are now slightly more probable.

### Bug Fixes

* Fixed a bug that allowed a slave to be ransomed multiple times while waiting for a reply.
* Fixed a bug that allowed a slave to be ransomed for a different than the agreed ransom cost if the payer short term gold changed meanwhile.
* Fixed *Buy Foreign Slaves* and *Runaway Slave* events often firing at the same time.

### Housekeeping

* Refactored slave interactions to use `is_character_interaction_potentially_accepted` and removed obsolete `ai_accept` values.
* Added a prefix with the character name and id to debug logs.

## Version 0.14.0

### Compatibility

* Adapted to CK3 1.10.0

### Court Positions

* Enabled *Wet Nurse* court position to be assigned to slaves
* Nerfed slave court position modifiers

### Events

* Further reduced *Buy Foreign Slaves* slave prices for the AI

## Version 0.13.1

### Slavery Attitudes

* Reduced impact of slavery attitudes on AI willingness to initiate and accept slavery interactions.

### Bug Fixes

* Added support for dynamic faith hostility in total conversion mods such as EK2

## Version 0.13.0

### Interactions

* Added *Offer Ransom for Slaves* interaction (`carnx_pay_ransom_slaves_interaction`). Offer ransom to other rulers for one of their slaves who is your relative. This is a convenience interaction for the human player to quickly find all slaves they could offer ransom for.
* Added *Demand Ransom for Slaves* interaction (`carnx_ransom_slaves_interaction`). Demand ransom for some of your slaves from other rulers who are their relatives. This is a convenience interaction for the human player to quickly find all rulers able and willing to pay ransom for their slaves.

### Slavery Attitudes

* Added *Choose Slavery Attitude* decision and event. Choose a slavery attitude, one of *Slaver*, *Liberator*, *Slave Trader*, or *Slave Employer* to get a minor modifier and a unique slavery-related perk.
* Added impact of slavery attitudes on AI willingness to initiate and accept slavery interactions.

### Miscellaneous

* Improved event themes and backgrounds.

### Housekeeping

* Added debug logging of freeing illegal slaves.

## Version 0.12.2

### Bug Fixes

* The AI will no longer send empty ransom offers to the player.

## Version 0.12.1

### Compatibility

* Adapted to CK3 1.9.2

## Version 0.12.0

### Interactions

* Added *Offer Ransom for Slave* interaction (`carnx_pay_ransom_slave_interaction`). Offer ransom for a slave who is your relative or shares your faith. The player (but not the AI) may also offer ransom for slaves of their own faith, even if they are not relatives.
* Renamed *Ransom Slave* interaction (`carnx_ransom_slave_interaction`) to *Demand Ransom for Slave* and thoroughly reworked it for consistency with *Offer Ransom for Slave* and other interactions.
* Added *Liberate Slave* interaction (`carnx_liberate_slave_interaction`). Liberate somebody else's slave who is your prisoner and ask for gold, conversion, renouncing of claims, a favor, or nothing in return.
* Reworked *Free Slave* interaction (`carn_free_slave_interaction`) for consistency with other interactions.
* Added *Slavery* interaction category and moved most slave interactions to it.
* Added a new slave memory when a slave was liberated.

### Events

* Added an option to buy both slave in *Buy Foreign Slaves* event. This option is only available to the player.

### Miscellaneous

* Added "The Slaver" and "Breaker of Chains" nicknames. They may be acquired via an event after acquiring the corresponding *Slaver* and *Liberator* traits.
* Enabled trading of slaves between players in multiplayer games.
* Slightly increased slave court position salaries.
* Slightly increased the opinion gain from gifting a slave and set its minimum to 10.

### Bug Fixes

* Fixed `secondary_recipient` localization in *Sell Slave* interaction.
* Fixed a rare error caused by missing `target` in the `carnx_on_set_relation_rival` on-action.
* Fixed a rare error caused by missing `imprisoner` in `carn_button_prison_enslave` scripted gui (Carnalitas bug).
* Ensured a prisoner can only be hired as an executioner if the strong hook on them is usable (vanilla bug).
* Added placeholder tradition for Carnalitas cultural parameters to avoid errors in `error.log` (Carnalitas bug).

### Localization

* Added Russian localization by [@Undertalk](https://www.loverslab.com/profile/9955238-undertalk/).

### Housekeeping

* Added debug logging of slave conversion events

## Version 0.11.1

### Compatibility

* Adapted to CK3 1.9.1

### Bug Fixes

* Free Slave interaction now longer checks if the slave can be sold

## Version 0.11.0

### Interactions

* Added wealth considerations for the AI when buying and selling slaves
* Changed age considerations so that non-prime age impacts negatively, instead of prime age impacting positively
* Added "lacking councillors, court positions, knights, or commanders" considerations for the seller / owner
* Halved impact of claims held by slaves on AI decision making
* Slightly increased impact of being a female and reduced impact of age
* Slightly reduced impact of opinion by reducing AI opinion multiplier
* Changed slave base price calculation to correspond to the above changes
* Increased slave base price multiplier from 0.6 to 0.75
* Reduced aptitude threshold for some court positions
* Reduced "Buy Foreign Slaves" event chance for "none" option

## Version 0.10.1

### UI

* Added trait and interaction icons

## Version 0.10.0

### Compatibility

* Adapted to CK3 1.9 and Carnalitas 2.0
  * Adapted changes to vanilla council and court positions
  * Adapted changes to vanilla triggers, effects, and values
  * Adapted to new vanilla tiered lifestyle traits
  * Ensured there are no `carnx` errors in the error log

## Version 0.9.0

### Interactions

* Religious doctrines now impact also selling and gifting slaves. These interactions can no longer be initiated and are not accepted if illegal, and have a piety cost if shunned.
* Added progress towards rival when enslaving a character.
* Made vengeful characters more willing to join schemes against the person who originally enslaved them.

### Traits

* Added *Slaver* trait. This is a fame trait that adds negative diplomacy, prestige, MAA maintenance, and general opinion, and positive dread multipliers. It is acquired via an event after enslaving and then selling a certain number of people, usually between 20 and 30.
* Added *Liberator* trait. This is a fame trait that adds positive diplomacy, prestige, MAA maintenance, and general opinion, and negative dread multipliers. It is acquired via an event after freeing or ransoming a certain number of people, usually between 20 and 30.

### Events

* Added *Infamous Slaver* event (`carnx_slave.0006`) for a character to acquire the *Slaver* trait after selling someone originally enslaved by them.
* Added *Famous Liberator* event (`carnx_slave.0007`) for a character to acquire the *Liberator* trait after freeing or ransoming someone not originally enslaved by them.

### Bug Fixes

* Fixed a rare error caused by trying to use a hook without a usable hook.

## Version 0.8.0

### Interactions

* Ensured that piety is appropriately lost also when buying, seizing, or accepting a slave as a gift if slavery is not accepted according to doctrines.
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

* AI rulers may have sex with one of their slaves (or former slaves who are also *Slave Concubines*) once a year if they are attracted to them.
  * This applies also to the human player if the *Make Love* interaction is disabled.
  * The chance of pregnancy is for the moment hardcoded at 10%.

### Bug Fixes

* Former slaves who are married are no longer eligible to become *Slave Concubines*.
* It is now possible to *Make Love* to a former slave that is also a *Slave Concubine*.

## Version 0.5.0

### Miscellaneous

* Characters who can be enslaved and have a base price higher than a threshold are now captured instead of killed during raids and sieges.
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

* Increased the percentage of slaves who are enslaved when imprisoned vs. generated by the *Buy Foreign Slaves* event (from 28% to 41%).
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
* Changed *Sell Slaves* to show only slaves who can actually be sold to somebody.
* Ensured the AI replies immediately to *Buy Slave* and *Sell Slave* offers.
* Enabled the use of hooks in *Buy Slave* and *Sell Slave* interactions.
* Added "price considerations" AI modifier to *Buy Slave* and *Sell Slave* interactions. When buying, the AI is now more willing to buy slaves who are cheap (price < `minor_gold_value`) and less willing to buy slaves who are expensive (price > `major_gold_value`), and vice versa when selling.
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
* Modified *Seize Slave* interaction (`carn_seize_slave_interaction`). Seize somebody else's slave who is your prisoner.
* Added *Buy Slaves* interaction (`carnx_buy_slaves_interaction`). Buy slaves from other rulers who are willing to sell them to you. This is a convenience interaction for the human player to quickly find all slaves they could buy and the prices at which they could be bought. Slaves are bought at the seller's price (`carnx_slave_ask_price_value`).
* Added *Sell Slaves* interaction (`carnx_sell_slaves_interaction`). Sell some of your slaves to other rulers willing to buy them from you. This is a convenience interaction for the human player to quickly find all potential buyers for their slaves and the prices at which they could be sold. Slaves are sold at the buyers's price (`carnx_slave_bid_price_value`)
* Added *Ransom Slave* interaction (`carnx_ransom_slave_interaction`). Ransom one of your slaves with another ruler who is their relative or relation for either gold or a favor. If asked for gold and accepted, the payer pays the slave's ransom cost (`carnx_slave_ransom_cost_value`).
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
