# Carnalitas Slavery Reimagined

## Overview

[Carnalitas](https://www.loverslab.com/files/file/14207-carnalitas-unified-sex-mod-framework-for-ck3/) added a much-needed slavery system to CK3. While this is great in itself and many aspects of the original system are also very well thought of, I find other aspects rather lacking, perhaps due to Carnalitas ambition to be a "unified sex mod framework" rather than a well-balanced mod in its own right.

Some of the aspects I find problematic are the following:

* The slave prices don't correspond well to other aspects of the game. The prices for slaves with claims are rather insane. Without claims, they are much too cheap, so a human player could buy a useful slave for a small fraction of the cost of recruiting a guest with the same qualities. Some of the factors that should influence the slave price (e.g. their attraction) are not taken into account at all.
* Most of the slave interactions are accepted or initiated by the AI for the wrong reasons. For example, the factors behind the AI decision to enslave are basically copied from the *Execute* interaction. However, enslaving is not the same as executing and should be influenced by quite different factors. The situation is quite similar for other interactions, e.g. *Buy Slave*, *Sell Slave*, etc.
* The AI will never perform some of the interactions, e.g. it will try to buy slaves from other rules, but never sell their own slaves to them.
* It's not exactly easy for the human player to find rulers that are willing to buy one of your slaves, or sell some of their slaves to you. Indeed this doesn't matter much, since in Carnalitas such requests almost always are accepted, and always at the same price.
* I don't really appreciate the idea of being able to "convince" someone to become your slave (*Enslave* being possible on free courtiers). Enslaving someone is a rather brutal act that should only be possible if he or she is fully at your mercy (your prisoner).
* Once a prisoner is converted to a slave, it's no longer possible to ransom him or her. True, you can instead sell them to e.g. their mother, and the mother will happily become their new owner, but I find this rather disconcerting.
* Although there are religious doctrines that should govern whether owning slaves of certain faiths is considered a crime, shunned, or accepted, they are not followed consistently when determining if someone can be enslaved, bought, or seized.

This mod attempts to address the above shortcomings. It does this by reworking some of the slave interactions and introducing a few new ones. It aims to be compatible with other Carnalitas features and with other mods based on Carnalitas.

The reimagined slavery system introduced by this mod tries to better integrate slavery into the existing aspects of the game, make interacting with slaves and other rulers more interesting and rewarding, achieve a better game balance, and maintain a reasonable challenge for the human player.

## Features

### Buying and Selling Slaves

As in Carnalitas, slaves can be bought or sold via the *Buy Slave* and *Sell Slave* interactions. There are however substantial differences in how these interactions work in this mod.

#### Slave Prices

In this mod, slaves are bought and sold at prices that better reflect their actual value. Most of the factors inflencing the base price of a slave are the same as those influencing the cost of recruiting a guest, with similar impact:

* base (10)
* claims (100 to 250)
* dynasty prestige level (5 per level)
* genetic traits (5 per level of good trait, -5 per level of bad trait)
* commander traits (15 per trait)
* court physician traits (10 to 20)
* skills (5 per skill point above 12)

Some factors are unique:

* attraction (-10 to 20)
* visibly fertile female (20)

Slave prices thus can range from almost nothing to rather exorbitant sums, and unlike Carnalitas prices they much better correpond to other existing aspects of the game.

Actual buy and sell transactions are settled at the *bid price* (buyer's price) if the initiating party is the seller, and the *ask price* (seller's price), if the initiating party is the buyer.These prices are calculated by multiplying the base price by a factor ranging from 0.8 to 1.2, depending on AI greed.

These prices are also multiplied by an additional factor of 0.8 (for the bid price) or 1.2 (for the ask price) if the initiating party is the human player. Since the human player is always the initiating party when buying or selling slaves, the conditions are always unfavorable. This is to prevent exploits, and to make it a bit more challenging for the human player to use the slavery system to their own advantage.

#### AI Willingness to Buy or Sell

When buying slaves, the AI acceptance is influenced by a comprehensive estimation of the slave's usefulness based on factors such as:

* Is the buyer lacking councillors, court physician, or knights, and how well would the slave perform the corresponding role.
* Does the slave have any useful claims on neighbouring realms.
* Is the buyer attracted to the sex of the slave, and if yes the slave's attraction.
* Is the slave a visibly fertile female.

When selling, the AI acceptance is influenced by similar factors, but working in the opposite direction. Factors such as the AI's opinion of the other party play a minor role, and dread plays no role at all. In addition, the AI will only buy if their "short term gold" exceeds a certain threshold, and will only sell if the other party has enough gold to pay the agreed price.

When deciding to initiate buying or selling of slaves, the AI is driven by much the same considerations. Unlike Carnalitas, AI rulers will attempt to both buy and sell slaves from / to other AI rulers (never the human player).

All in all, AI is in general quite reluctant to buy slaves that are useless, or sell slaves that are useful to them. As a human player, you may find it impossible to find buyers for your slaves unless they have some of the useful qualities listed above. So instead of enslaving just about everybody you come across, you may want to consider whether you would be able to sell them first.

#### Convenience Interactions for the Human Player

While it is possible to initiate buying or selling of slaves by right-clicking on a ruler, it may be quite hard to find rulers that are willing to buy one of your slaves, or sell some of their slaves to you. Furthermore, the price you get with each ruler may be different. To make it more convenient for the human player, this mod introduces the following 2 new interactions:

* *Buy Slaves*: Buy a slave by choosing from the list of all slaves that other rulers are willing to sell to you.
* *Sell Slaves* Sell one of your slaves by choosing from the list of all other rulers that are willing to buy that slave from you. If there are no potential buyers for a slave, the list will be empty.

### Enslaving and Seizing Prisoners

As in Carnalitas, prisoners can be enslaved via the *Enslave* interaction. If the prisoner is already someone else's slave, he or she can be "seized" via the *Seize Slave* interaction.

Unlike Carnalitas, a person can only be enslaved if he or she is a prisoner. The *Enslave* interaction is not available on free courtiers. Since a prisoner doesn't really have a choice, both *Enslave* and *Seize Slave* interactrions are accepted automatically.

When deciding to initiate enslaving or seizing of slaves, the AI is driven by considerations similar to the ones listed under [AI Willingness to Buy or Sell](#ai-willingness-to-buy-or-sell). In addition, factors such as AI compassion, greed, and their opinion of the prisoner also play a role. Unlike Carnalitas, the AI would rather not enslave a prisoner if he or she should rather be executed (execution reason, rival / nemesis, unfaithful spouse, etc.), unless the prisoner survived for more than 2 years.

### Freeing and Ransoming Slaves

As in Carnalitas, slaves can be freed by their owners via the *Free Slave* interaction. In return the owner may ask for gold, conversion, renouncing of claims, a favor, or nothing. In this mod it is also possible to ransom a slave with another ruler that is their relative or relation for either gold or a favor, via the new *Ransom Slave* interaction.

When deciding to initiate freeing or ransoming of slaves, the AI is driven by considerations similar to the ones listed under [Enslaving and Seizing Prisoners](#enslaving-and-seizing-prisoners), but working in the opposite direction.

Note that the cost of freeing or ransoming a slave is not their slave price, but their usual [ransom cost](https://ck3.paradoxwikis.com/Court#Ransom_cost). If you enslaved a prisoner instead of ransoming, you won't be able to sell the slave back to a relative at their slave price (relatives get additional maluses to their willingness to buy), but you would still be able to ransom - potentially for less money, since the slave is no longer a spouse or an heir.

### Impact of Slavery Doctrines

Carnalitas introduces the *Slavery Crime* and *Slavery Shunned* religious doctrines that determine whether owning slaves of certain faiths is considered a crime, shunned, or accepted, depending on the faith's hostility level. However, in Carnalitas these doctrines are not followed consistently when determining if someone can be enslaved, bought, or seized, the AI acceptance of slave interactions, or the AI decisions to initiate them. This mod attempts to correct this by reexamining the impact of slavery doctrines on all slave interactons:

* If owning slaves of a certain faith is a crime, for adherents of this faith:
  - It is not possible to enslave, seize, or buy them for the human player. The AI will not initiate such interactions at all.
  - The AI will not accept sell interactions for them.
  - The AI will be quite willing to free or ransom them.
* If owning slaves of a certain faith is shunned, for adherents of this faith:
  - The AI will be quite unwilling to enslave, seize, or buy them.
  - The AI will be quite unwilling to accept sell interactions for them.
  - The AI will be somewhat more willing to free or ransom them.

### Slavery Events

For the moment, there is just one additional slavery event introduced by this mod.

* *Buy Foreign Slaves*: Slave traders bring two slaves for sale and you can buy one of them. The slaves are of faith and culture that is different from yours, and never of faith that falls under the *Slavery Crime* doctrine. One of the slaves has skills / traits that make him or her more valuable, for the other one they are generated completely at random.

Besides adding flavor, the above event serves the purpose of "seeding" the game with more slaves that would normally exist if the only way to create them was to enslave prisoners. It will fire approximately every 5 years for every ruler of rank count and above. The AI will mostly not buy, unless it considers one of the slaves really useful according to the factors described in [AI Willingness to Buy or Sell](#ai-willingness-to-buy-or-sell).

### Slave Memories

Being enslaved, freed, bought, or seized is certainly a significant lifetime event from the slave's perspective. This mod adds character memories for all these events in the slave's memory book.

### Bug Fixes

The following bugs present in Carnalitas have been fixed in this mod:

* If a slave owner dies and their heir doesn't inherit their court (e.g. because they have their own court), slaves don't just wander off similarly to other courtiers, but are instead added to the court of their new owner.
* If a slave owner stops being a ruler, their slaves are freed automatically. Non-rules owning slaves is problematic because they are not under AI control and their slaves can never be freed, ransomed, or traded.

## Compatibility

This mod requires [Carnalitas](https://www.loverslab.com/files/file/14207-carnalitas-unified-sex-mod-framework-for-ck3/) as a prerequisite (obviously). While it modifies the slavery system in a substantial way, it doesn't touch other Carnalitas features and should be compatible with all of them. It is also compatible with other popular mods based on Carnalitas that don't modify the slavery system, such as [CBO](https://www.loverslab.com/files/file/16683-character-body-overhaul/), [CBO Carnal Court](https://www.loverslab.com/files/file/21059-cbo-carnal-court/), [Physical Attributes](https://www.loverslab.com/files/file/16927-physical-attributes/), etc. It is not compatible with mods that modify the slavery system, such as [Carnalitas Slavery Expansion](https://www.loverslab.com/files/file/21651-carnalitas-slavery-expansion/).

This mod is **NOT** compatible with the *Slavery System: Consensual Only* Carnalitas game rule (`carn_slavery_content_consensual_only`).

## Changes to Carnalitas

The sections below list the changes made to existing Carnalitas objects in somewhat more detail.

### Interactions

This mod replaces the following Carnalitas interactions, modifying them as described above:

* **Buy Slave** (`carn_buy_slave_directly_interaction`): Buy a slave from another ruler. If accepted, the slave is bought at the seller's price (`carnx_slave_ask_price_value`).
* **Sell Slave** (`carn_sell_slave_interaction`): Sell one of your slaves to another ruler. If accepted, the slave is sold at the buyers's price (`carnx_slave_bid_price_value`).
* **Enslave** (`carn_enslave_interaction`): Enslave one of your prisoners.
* **Free Slave** (`carn_free_slave_interaction`): Free one of your slaves, potentially asking for gold, conversion, renouncing of claims, or a favor. If asked for gold and accepted, the slave pays their ransom cost (`carnx_slave_ransom_cost_value`).
* **Seize Slave** (`carn_seize_slave_interaction`): Seize somebody else's slave that is your prisoner.

This mod introduces the following new interactions:

* **Buy Slaves** (`carnx_buy_slaves_interaction`): Buy slaves from other rulers that are willing to sell them to you. This is a convenience interaction for the human player to quickly find all slaves they could buy and the prices at which they could be bought. Slaves are bought at the seller's price (`carnx_slave_ask_price_value`).
* **Sell Slaves** (`carnx_sell_slaves_interaction`): Sell some of your slaves to other rulers willing to buy them from you. This is a convenience interaction for the human player to quickly find all potential buyers for their slaves and the prices at which they could be sold. Slaves are sold at the buyers's price (`carnx_slave_bid_price_value`)
* **Ransom Slave** (`carnx_ransom_slave_interaction`): Ransom one of your slaves with another ruler that is their relative or relation for either gold or a favor. If asked for gold and accepted, the payer pays the slave's ransom cost (`carnx_slave_ransom_cost_value`).

### On Action

TODO

### Effects

TODO

### Triggers

TODO
