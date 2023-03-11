# Carnalitas Slavery Reimagined

A comprehensive rework of the Carnalitas slavery system aiming at improved balance and better integration with other aspects of the game.

## Overview

[Carnalitas](https://www.loverslab.com/files/file/14207-carnalitas-unified-sex-mod-framework-for-ck3/) added a much-needed slavery system to CK3. While this is great in itself and the basics of the original system are solid, there are certain things that could be improved, perhaps due to Carnalitas ambition to be a "unified sex mod framework" rather than a well-balanced mod in its own right.

In particular:

* Slave prices don't correspond well to other aspects of the game, they are way to high with claims and way to low otherwise.
* The reasons behind the AI accepting or initiating slave interactions are not convincing, and the AI never initiates some of them.
* It's not exactly easy for the human player to find rulers willing to buy or sell slaves, and there are rather few slaves owned by the AI to begin with.
* *Enslave* is possible on free courtiers, which doesn't make much sense.
* Once a prisoner is converted to a slave, it's no longer possible to ransom him or her.
* Religious doctrines that govern whether owning slaves of certain faiths is considered a crime, shunned, or accepted, are not followed consistently when determining if someone should be enslaved, freed, bought, or seized.

In a nutshell, what you can do as a human player is easily enslave a lot of people, sell any you don't need to the AI, and buy any you may fancy from the AI, while the AI mostly passively obliges. With mods such as [Carnalitas Slavery Expansion](https://www.loverslab.com/files/file/21651-carnalitas-slavery-expansion/) you can also assign them "professions" for additional benefits. However, these are also human-only, the AI never assigns them. All of this undermines the realism and immersion, and makes the game both a lot easier and less interesting than it could be.

This mod introduces a redesigned slavery system, one aiming to better integrate slavery with other aspects of the game, make interacting with slaves and other rulers more interesting and rewarding, achieve a better game balance, and maintain a reasonable challenge for the human player. It does this by reworking most of the slave interactions, introducing some new ones, making slaves more desirable for council and court positions, adding slave-related events, and rebalancing or fixing many of the original effects and outcomes, while still maintaining compatibility with other Carnalitas features, other mods based on Carnalitas, and total conversion mods.

With this mod:

* The AI competes actively in obtaining the best slaves, taking into account factors such as skills, aptitudes, claims, attraction, age, price, current jobs and more when buying, selling, enslaving or freeing.
* Slave prices better reflect the actual usefulness of slaves.
* It's much easier to find rulers willing to buy or sell slaves via special convenience interactions.
* Slavery doctrines have a significant and consistent impact that better reflects their original meaning.
* Slaves can be also ransomed or gifted.
* Slaves can be assigned to (some, but not all) council and court positions for additional benefits, and the AI is fully capable of doing this as well.
* There are new court positions reserved for slaves or former slaves, such as *Slave Concubine* or *Mameluke Captain*, available depending on religion, culture, and government form.
* Additional slaves fit for specific occupations are spawned into the world via events.

All taken together, slaves are now genuinely useful to their owners, there is an actual demand for them conditioned by religion and culture, and this demand is satisfied by active enslaving, slave trade, and slave-related events. As a human player, you can still use the system to your advantage, but it's more challenging and hopefully more interesting to do this.

## Features

### Buying and Selling Slaves

As in Carnalitas, slaves can be bought or sold via the *Buy Slave* and *Sell Slave* interactions. There are however substantial differences in how these interactions work in this mod.

#### Slave Prices

In this mod, slaves are bought and sold at prices that better correspond to the cost of recruiting guests. Most of the factors influencing the base price of a slave are the same as those influencing the cost of recruiting a guest, with similar impact, such as base, claims, dynasty prestige level, genetic, commander, and other traits, and skills. There are also some unique factors, such as attraction, visibly fertile female, and age. At the very end, a correction multiplier is applied to calculate the final base price, intended to prevent the human player from making too much money from selling slaves.

Actual buy and sell transactions are settled at the *bid price* (buyer's price) if the initiating party is the seller, and the *ask price* (seller's price), if the initiating party is the buyer.These prices are calculated by multiplying the base price by a factor ranging from 0.8 to 1.2, depending on AI greed. These prices are also multiplied by an additional factor of 0.8 (for the bid price) or 1.2 (for the ask price) if the initiating party is the human player. Since the human player is always the initiating party when buying or selling slaves, they always buy at higher and sell at lower prices. This is to prevent exploits, and to make it a bit more challenging for the human player to use the slavery system to their own advantage.

#### AI Willingness to Buy or Sell

When buying slaves, the AI acceptance is influenced by a comprehensive estimation of the slave's usefulness based on factors such as:

* Is the slave better than other options available to the buyer as a councillor, court position (any of 14 existing and 2 new specific to slaves), knight, or commander, and how much better exactly.
* Does the slave have any useful claims on neighboring realms.
* Is the buyer attracted to the sex of the slave, and if yes the slave's attraction.
* Is the slave a visibly fertile female.
* The age of the slave, peaks between 16 and 30 years of age (only applies to slaves that are considered useful for some of the above reasons).
* The slave price.

When selling, the AI acceptance is influenced by similar factors, but working in the opposite direction. Factors such as the AI's opinion of the other party play a minor role, and dread plays no role at all. In addition, the AI will never offer to pay more than their "short term gold" (the portion of the AI's budget that can be used for short term purchases), and will only sell if the other party offers enough gold to pay the full price.

When deciding to initiate buying or selling of slaves, the AI is driven by much the same considerations. Unlike Carnalitas, AI rulers will attempt to both buy and sell slaves from / to other AI rulers (never the human player).

All in all, the AI is in general quite reluctant to buy slaves that are useless, or sell slaves that are useful to them. As a human player, you may find it impossible to find buyers for your slaves unless they have some of the useful qualities listed above. Still, for slaves that nobody wants to buy, there are plenty of other options what to do with them. You could also spend a hook if you have one on a ruler and really want to buy or sell a slave.

#### Convenience Interactions for the Human Player

While it is possible to initiate buying or selling of slaves by right-clicking on a ruler, it may be quite hard to find rulers that are willing to buy one of your slaves, or sell some of their slaves to you. Furthermore, the price you get with each ruler may be different. To make it more convenient for the human player, this mod introduces the following 2 new interactions:

* *Buy Slaves*: Buy a slave by choosing from the list of all slaves that other rulers are willing to sell to you. If there are no such slaves, the list will be empty.
* *Sell Slaves*: Sell one of your slaves by choosing from the list of all other rulers that are willing to buy that slave from you. If there are no potential buyers for a slave, the list will be empty.

### Enslaving and Seizing Prisoners

As in Carnalitas, prisoners can be enslaved via the *Enslave* interaction. Prisoners that are already someone else's slaves can be "seized" instead via the *Seize Slave* interaction.

Unlike Carnalitas, a person can only be enslaved if he or she is a prisoner. The *Enslave* interaction is not available on free courtiers. Since a prisoner doesn't really have a choice, both *Enslave* and *Seize Slave* interactions are accepted automatically.

When deciding to initiate enslaving or seizing of slaves, the AI is driven by considerations similar to the ones listed under [AI Willingness to Buy or Sell](#ai-willingness-to-buy-or-sell). In addition, factors such as AI compassion, greed, and their opinion of the prisoner also play a role. Unlike Carnalitas, the AI would not enslave a prisoner that should rather be executed (execution reason, rival / nemesis, unfaithful spouse, etc.), unless the prisoner survived for more than 2 years.

### Freeing and Ransoming Slaves

As in Carnalitas, slaves can be freed by their owners via the *Free Slave* interaction. In return the owner may ask for gold, conversion, renouncing of claims, a favor, or nothing. In this mod it is also possible to ransom a slave with another ruler that is their relative or relation for either gold or a favor, via the new *Ransom Slave* interaction.

When deciding to initiate freeing or ransoming of slaves, the AI is driven by considerations similar to the ones listed under [Enslaving and Seizing Prisoners](#enslaving-and-seizing-prisoners), but working in the opposite direction.

Note that the cost of freeing or ransoming a slave is not their slave price, but their usual [ransom cost](https://ck3.paradoxwikis.com/Court#Ransom_cost). If you enslaved a prisoner instead of ransoming, you won't be able to sell the slave back to a relative at their slave price (relatives get additional negative modifiers to their willingness to buy), but you would still be able to ransom - potentially for less money, since the slave is no longer a spouse or an heir.

### Gifting Slaves

In this mod, a slave can also be gifted to another ruler for an opinion gain via the new *Gift Slave* interaction. The opinion gain is proportional to the slave base price and to the "gift opinion / gift value" ratio of the *Send Gift* vanilla interaction. AI rulers are much more likely to accept slaves as gifts than to buy them.

### Impact of Slavery Doctrines

Carnalitas introduces the *Slavery Crime* and *Slavery Shunned* religious doctrines that determine whether owning slaves of certain faiths is considered a crime, shunned, or accepted, depending on the faith's hostility level. However, in Carnalitas these doctrines are not followed consistently when determining if someone can be enslaved, bought, or seized, the AI acceptance of slave interactions, or the AI decisions to initiate them. This mod attempts to correct this by rebalancing the impact of slavery doctrines on all slave interactions:

* If owning slaves of a certain faith is a crime, for adherents of this faith:
  - It is not possible to enslave, seize, or buy them for the human player. The AI will not initiate such interactions at all.
  - The AI will not accept sell interactions for them.
  - The AI will be quite willing to free or ransom them.
* If owning slaves of a certain faith is shunned, for adherents of this faith:
  - The AI will be quite unwilling to enslave, seize, or buy them.
  - The AI will be quite unwilling to accept sell interactions for them.
  - The AI will be somewhat more willing to free or ransom them.

### Council and Court Positions

Starting with version 0.4.0, this mod integrates the slavery system also with council and court positions. The overall idea is somewhat similar to the "slave professions" in the Slavery Expansion mod, but using court positions has a number of advantages - they are much more sophisticated, the AI can take full advantage of them, they can be restricted by religion, culture, and government type, etc.

### New Slave Court Positions

This mod introduces 2 new court positions that are reserved for slaves or former slaves conferring somewhat lesser but still tangible advantages:

* *Slave Concubine*: diplomacy / attraction, restricted to polygamous religions and cultures, gives court grandeur and prestige (5 positions)
* *Mameluke Captain*: martial / prowess, restricted to clan governments, gives court grandeur and knights effectiveness (3 positions)

More slave court positions will be added in future versions.

### Changes to Existing Council and Court Positions

This mod divides the existing council and court positions into ones that are available to slaves (always or only for certain government forms), and ones that are not available to slaves at all.

The following 14 court positions are available to slaves: *Court Physician*, *Antiquarian*, *Court Gardener*, *Court Tutor*, *Food Taster*, *Seneschal*, *Cupbearer*, *Chief Eunuch*, *Court Jester*, *Court Poet*, *Court Musician*, *Bodyguard*, *Personal Champion*, and *Executioner*. The rest of the court positions are not available to slaves, because they are considered either ceremonial (reserved for vassals to make them happy) or religious, or are subject to certain game limitations.

The following 4 council positions are available to slaves: *Chancellor*, *Steward*, *Marshal*, and *Spymaster*. The *Court Chaplain* council position is not available to slaves, since it is considered religious. Note that *Chancellor*, *Steward*, and *Marshal* are only available to slaves if your government is clan or tribal, to reflect the fact that historically such important roles were held by slaves only if they were considered more loyal than other available options, which was the case in certain Muslim and tribal societies.

Once a slave is assigned to a court position, he or she is paid a reduced salary (25%) and has an increased opinion gain (3x) compared to other courtiers. AI rulers are therefore more likely to appoint slaves to court positions.

When evaluating slaves for buying, selling, enslaving, etc., the AI considers their fitness for all these positions. Slaves that are evaluated as useful usually end up actually being used (employed in a council or court position) by the AI.

### Slavery Events

For the moment, there is just one additional slavery event introduced by this mod.

* *Buy Foreign Slaves*: Slave traders bring two slaves for sale and you can buy one of them. The slaves are of faith and culture that is different from yours, and never of faith that falls under the *Slavery Crime* doctrine. One of the slaves has skills / traits that make him or her a better fit for a particular occupation, for the other one they are generated completely at random.

Besides adding flavor, the above event serves the purpose of spawning more slaves that would normally exist if the only way to create them was to enslave prisoners. It will fire approximately every 5 years for every ruler of rank count and above. The AI will mostly not buy, unless it considers one of the slaves really useful according to the factors described in [AI Willingness to Buy or Sell](#ai-willingness-to-buy-or-sell).

### Slave Memories

Being enslaved, freed, bought, ransomed, seized, or gifted is certainly a significant lifetime event from the slave's perspective. This mod adds character memories for all these events in the slave's memory book.

### Bug Fixes

The following bugs present in Carnalitas have been fixed in this mod:

* If a slave owner dies and their heir doesn't inherit their court (e.g. because they have their own court), slaves don't just wander off similarly to other courtiers, but are instead added to the court of their new owner.
* If a slave owner stops being a ruler, their slaves are seized by the new title holder of their last title. Non-rulers owning slaves is problematic because they are not under AI control and their slaves can never be freed, ransomed, or traded.
* Enslaved concubines are properly "divorced".

## Vanilla Changes

* Slaves can be imprisoned without incurring tyranny (and dread). Prisoner interactions on the imprisoned slave are not affected by their slave status.
* Slaves are less likely to be converted to their owner's faith compared to other courtiers. This is mostly to prevent too many slaves to be freed too quickly as a result of the rebalanced impact of slavery doctrines.

## Compatibility

This mod requires [Carnalitas](https://www.loverslab.com/files/file/14207-carnalitas-unified-sex-mod-framework-for-ck3/) as a prerequisite (obviously). While it modifies the slavery system in a substantial way, it doesn't touch other Carnalitas features and should be compatible with all of them.

### Compatibility with Mods Based on Carnalitas

This mod should be compatible with all mods based on Carnalitas that don't modify the slavery system. Compatibility with the following mods has been explicitly verified, but most others should work as well:

* [CBO](https://www.loverslab.com/files/file/16683-character-body-overhaul/)
* [CBO Carnal Court](https://www.loverslab.com/files/file/21059-cbo-carnal-court/)
* [Physical Attributes](https://www.loverslab.com/files/file/16927-physical-attributes/)

This mod may not be compatible with all other mods that modify the slavery system. However, it should still be compatible with mods that don't change the original Carnalitas slave interactions, modifiers, or effects. Compatibility with the following mods has been explicitly verified:

* [Carnalitas Slavery Expansion](https://www.loverslab.com/files/file/21651-carnalitas-slavery-expansion/).

### Compatibility with Carnalitas Slavery System Rules

This mod is fully compatible with the *Slavery System: Disabled* and *Slavery System: Enabled* Carnalitas game rules. If the slavery system is disabled, all interactions and events introduced or modified by this mod will be disabled too, and vice versa.

This mod is not compatible with the *Slavery System: Consensual Only* Carnalitas game rule. If this option is chosen, the effect will be exactly the same as with *Slavery System: Enabled*.

### Compatibility with Total Conversion Mods

Due to the changes mentioned in [Changes to Existing Council and Court Positions](#changes-to-existing-council-and-court-positions), this mod may overwrite changes to council and court positions by total conversion mods. For best experience, such mods now require compatibility patches.

Compatibility patches for [Elder Kings 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2887120253) and [Tales of Ireland](https://steamcommunity.com/sharedfiles/filedetails/?id=2453915294) are provided as separate downloads. I haven't checked compatibility with other total conversion mods, if you notice any issues please let me know.

## Changes to Carnalitas

The sections below list the changes made to existing Carnalitas objects in somewhat more detail for easier checking of compatibility with other mods.

### Interactions (`character_interactions`)

* *Buy Slave* (`carn_buy_slave_directly_interaction`): Modified as described above. If accepted, the slave is bought at the seller's price (`carnx_slave_ask_price_value`), not `carn_slave_price_value`.
* *Sell Slave* (`carn_sell_slave_interaction`): Modified as described above. If accepted, the slave is sold at the buyers's price (`carnx_slave_bid_price_value`), not `carn_slave_price_value`.
* *Enslave* (`carn_enslave_interaction`): Modified as described above.
* *Free Slave* (`carn_free_slave_interaction`): Modified as described above.
* *Seize Slave* (`carn_seize_slave_interaction`): Modified as described above. Added triggering of the `carnx_on_slave_seized` on-action.

### Effects (`scripted_effects`)

* `carn_enslave_effect`: Rebalanced (mainly slightly lowered) dread, tyranny, piety, and stress effects that were originally copied from the *Execute* interaction. Removed the removal of the slave's gold (it didn't work anyway and was reported in `errors.log`). Changed some tooltips.
* `carn_free_slave_effect`: Added a safety check to prevent errors in `carn_on_slave_freed`.
* `carn_free_slave_interaction_effect`: Rebalanced dread and piety effects. If asked for gold, the slave pays their ransom cost (`carnx_slave_ransom_cost_value`) instead of `carn_slave_price_value`.
* `carn_buy_slave_effect`: Changed interface messages and tooltips. Added triggering of the `carnx_on_slave_bought` on-action.

### On Action (`on_action`)

* `on_death_relation_slave`: Fixed some of the bugs mentioned in [Bug Fixes](#bug-fixes)

### Other

* The value `carn_slave_price_value` is no longer used by any interactions or effects. It has been replaced by other values, mainly `carnx_slave_bid_price_value` and `carnx_slave_ask_price_value`.
* The character and trait flags `carn_wants_to_be_a_slave` and the opinion modifier `carn_wants_to_be_your_slave_opinion` are no longer used by any interactions. They are intended to work with the `carn_slavery_content_consensual_only` game rule that is not supported.
