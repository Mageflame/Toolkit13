## Welcome to Toolkit13 (13th Age Compatible)

### What is Toolkit13 (13th Age Compatible)?

Toolkit13 is an Archmage Engine Compatible and 13th Age Compatible game System for FoundryVTT, enabling you to play any of the TTRPG's that utilize the core components of the Archmage Engine, such as Icon Relationships or Powers. The system includes 13th Age SRD content, such as Classes and Monsters.
Most of the system was written by asacolips#1867 (Discord), with cswendrowski#9701 joining later to assist.

### Quick System Overview

* Player Character Sheets can be created as a "Character" Actor
* PC's Attacks, Spells, Features, and Powers are created as "Power" items on the Character Sheet
* NPC / Monster Sheets can be created as a "NPC" Actor
* Magic Items can be created as "Equipment" Items, and will add their bonus to whatever Actor they belong to
* Mudane / Generic Items can be created as "Tool" or "Loot" Items
* Compendiums full of Monsters (NPC Actors) and Class Powers are available in the Compendium tab

### Combat 

#### Attack and Targeting Automation

Recommended Addons:
* https://foundryvtt.com/packages/easy-target/
* https://foundryvtt.com/packages/target-enhancements/

Both Player Powers and Monster Attacks often have "Triggers" - things like "Natural 15+", "Natural Even", "Natural Odd Hit".

For Triggers that rely only on the Natural roll such as "Natural 15+" or "Natural Even", they will always execute when rolled

// TODO: Image

For Triggers that rely on Hitting / Missing, the System will only evaluate the Trigger if 1+ Targets are selected. In the case of multiple Targets, each Target is evaluated separately for hits / misses, which is displayed in the final Chat message. For powers such as "1d3 in a group", you can select the max number (3) in the preference you want to hit them, and the System will pick them in that order in cases you roll less than max. If your target is random such as "1d3 random enemies in a group", the System will randomly pick instead.

// TODO: Image

Trigger evaluation is powered by Natural Language Processing (regexes, not full NLP AI) - all you need to do is type the power using the words we support.

// TODO: Full list of supported Triggers

##### Target Amount

1) Default - "far away target", "far away targets" - Checks attack against all selected targets
2) Amount - "1 nearby target", "3 nearby targets" - If more than specified number of targets is selected, only up to X (in the order of selection) is checked
3) Variable Amount - "`[[d2 + 2]]` nearby targets", "`[[d3]]` nearby targets in a group" - Evaluates the roll, then executes as if #2
4) Random Selection - "3 random nearby targets", "`[[d3]]` random far away targets" - As #3, except the targets are picked randomly instead of in-order

##### Natural Roll Triggers

1) Always - "Always:" - Always triggers
2) Hit - "Natural even hit:", "Hit:", "Natural Hit:" - Triggers when the natural attack roll matches or beats the target's defense
3) Miss - "Natural even miss:", "Miss:", "Natural Miss:" - Triggers when the natural attack roll is less than the target's defense
4) Even - "Natural even:", "Natural Even:" - Triggers with the natural attack roll is even
5) Odd - "Natural odd:", "Natural Odd:" - Triggers with the natural attack roll is odd
6) X+ - "Natural 6+:", "Natural 11+:" - Triggers when the natural attack roll matches or beats the target number such as 6
7) X - "Natural 1:", "Natural 20:", "Natural 10:" - Triggers when the natural attack roll exactly matches the target number such as 10
8) Crit - "Crit:" - Shorthand for "Natural 20"

#### Damage / Healing menu
You can right click a non-Attack roll to open a Context menu. This menu allows you to apply the roll as straight damage, half damage, double damage, triple damage, healing, or temporary health.

// TODO: Image

Please note that this will apply to the **Selected** token(s), ensuring that players can only apply damage to Tokens they control. The GM, as always, can select everything.

### Third Party Module Integrations

#### Iconic Relationship Point Card Support
As of 1.7.0, Iconic Relationship points can automatically give out Cards that represent them using this module: ![https://github.com/Brownie79/fvtt-card-support](https://github.com/Brownie79/fvtt-card-support)

![](https://cdn.discordapp.com/attachments/718595753852797012/746472772162814082/mageflame_icon_cards.gif)

Card support works with any SDF (Standard Deck Format) deck. You can use your own custom Icons and Cards so long as the Icon Relationship name in your Actor field matches the name in the metadata on the deck

Example from the included Mageflame Tarot Card SDF deck (![https://github.com/Mageflame/Toolkit13/blob/alpha/Mageflame%20Tarot%20Cards.zip](https://github.com/Mageflame/Toolkit13/blob/alpha/Mageflame%20Tarot%20Cards.zip): 
```yaml
name: The Gatekeeper 5
img: The Gatekeeper 5.jpg
back: The Gatekeeper 6.jpg
data:
    value: 5
    icon: The Gatekeeper
---
name: The Gatekeeper 6
img: The Gatekeeper 6.jpg
back: The Gatekeeper 5.jpg
data:
    value: 6
    icon: The Gatekeeper
```

For instructions on how to load the SDF deck, please see the Card Support documentation.

Once loaded, if a match is found on Iconic Relationship rolls, the correct cards will be dealt to players.

**Important Note:** As of time of writing, Card Support **requires** a GM to be logged in to work.
