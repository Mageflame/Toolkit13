## Welcome to Toolkit13 (13th Age Compatible)

### Enabling Icon Card Support
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
