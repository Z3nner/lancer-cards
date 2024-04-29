# INTENDED USE
Reactions in Lancer are reusable actions that generally occur outside of a player’s turn. Unless a more specific rule says otherwise, a player can use one reaction per turn, and an unlimited number of reactions per round. Reserves are special rewards players can typically use once to their advantage before the Reserve is expended.  Some newer, or less engaged players may have trouble tracking all of their available reactions and reserves.  Lancer Cards aims to help players to a better action economy.

If an In-person game used these cards, each player would have a few to several cards.  Everyone gets Overwatch and Brace and any other cards are determined by your licenses, Talents or earned Reserves.  If a player uses a Reaction they’d flip the corresponding card over and the back of the card would tell the player when they can use the card again. If a player uses a Reserve, typically one-time use, they’d discard the card, probably giving it back to the GM.  When using Foundry VTT, you’ll very likely want some module support to make the cards useable but that won’t change the intended use: if it’s a reaction, flip it over to declare when you use it, it tells you when you can use it again.  If it’s a reserve, discard it after you resolve it.

The GM can use the two decks included in this module to populate a deck of reactions and reserves for each player.  Depending on which module setup you prefer, you may also want to make a hand of cards for each player.

# SETUP

## Configure Deck Structure
* Import the two Card Decks from the Lancer Cards compendium by dragging them to your Card Stacks Tab. These will be referred to as the Master Decks.
* Create a Cards Deck for each of your players.
* Create a Cards Hand for each of your players. (Optional if using Card Tiles, Required for Card Hand Mini-Toolbar.)
* Create a single Cards Pile to act as a Discard pile.
* Give ALL players Observer permissions to ALL other player’s hand’s
* Give each player Owner permissions for their own hand.

Your deck structure should look something like this.

![DeckStructure](https://github.com/Z3nner/lancer-cards/assets/76132631/16946c88-3b88-4f71-9a0b-c5fe53fba374)

## Populate the Decks
From the Reactions Deck, drag Overwatch, Brace and any other reactions the player has from the Master Deck to the player’s Deck

There’s no automation here, you’re on your own to ensure you have all their reactions.

If players earn Reserves, they can be dragged from the Master Deck to the player’s deck using the same method.

(Note that placing a card in a Hand marks that card as drawn and prevents further use until the card is returned. Placing a card from one deck to another deck copies the card instead.)

![PopulateReactionDeck](https://github.com/Z3nner/lancer-cards/assets/76132631/51ebb399-ccde-4a55-956c-4210dce46e67)

Sometimes a player will have more cards than they can use. For example, a Hydra pilot has a reaction for each of its 3 Trait given drones, but the pilot has to pick one drone at a time. They’d have all the drone cards in their deck, but only the drone card they chose in their hand.)

So other than not choosing some options, like that Hydra's drone, you'll then take those cards you just copied to each player's deck, and "Deal" them to each player.

# USEFUL MODULES
In vanilla Foundry, Cards are pretty bare-bones.  You’ll most likely want to use some modules to add useability to these cards. There may be other modules out there that are even better.  If you find a better way to use these cards, I’d love to hear about it!

# Card Hand Mini Toolbar
https://foundryvtt.com/packages/hand-mini-bar

### SYNOPSIS
With this module, you’ll use a permanent (but minimizable) UI element to track and manage cards.
### SETUP
With a little setup from the GM on each player’s profile, each player’s hand of cards can be permanently overlayed on each player’s screen.

![CardHandMiniToolbarPreview](https://github.com/Z3nner/lancer-cards/assets/76132631/e8f8d73f-9fe6-4858-aa02-1559886b2ab1)

To see all player’s hands, find the module’s settings and set the Hand Count to the number of players in the game. While you’re in the settings, I recommend selecting the ‘Display Hand Name’ toggle and setting Card Click Behavior to ‘Open Hand’, the rest of the options are user choice.
This module saves its settings to the user’s browser, so you won’t be able to preconfigure your player’s mini-bars. However, using the Hook Macros module and the following macro, you can preset the options above, minimizing player work-load.

If you use the following macro, be sure to follow these requirements

• Set the value for the HandCount to be equal to the number of players in your game.

• Be sure the name of the macro you create, and its registration in Hook Macros module match exactly.

![MiniBarHookMacroConfig](https://github.com/Z3nner/lancer-cards/assets/76132631/d9b9ef5f-f9eb-4766-aeab-cb3ea9ebdf12)

```
setTimeout(() => {
game.settings.set("hand-mini-bar", "HandCount", 4);
game.settings.set("hand-mini-bar", "DisplayHandName", true);
}, 2000)
```

Instruct your players to click the Gear icon for each mini-bar and select a different player’s hand for each bar.

![MiniBarAssign](https://github.com/Z3nner/lancer-cards/assets/76132631/f4f99aaf-1212-49dc-8698-e087f9ce9dcf)

### USE
If the both the module and deck structure are configured as described above each player should be able to see every other player’s hand of cards and their own, and they should be able to interact with their own.
Conveniently, you can right click a card in the toolbar to flip it over. You can also drag cards directly to or from the mini-toolbars to other mini-toolbars or to Foundry’s default card stack windows.

# Card Tiles (Requires Monk’s Active Tile Triggers, a separate module)
https://foundryvtt.com/packages/card-tiles
### SYNOPSIS
With this option, when combat occurs, each player will place cards from their personal deck, onto the margins of the canvas. Clicking a card flips it over, but only a GM can move, edit or delete cards after they’ve been placed, only the GM can interact with Tiles.

![CardsToCanvas](https://github.com/Z3nner/lancer-cards/assets/76132631/ac5ad8b4-ae12-4836-b7e7-fad99c4cf06c)

### SETUP
Configure Card Tiles module settings according to the screenshot below

![CardTilesSettings](https://github.com/Z3nner/lancer-cards/assets/76132631/d1286e07-8e32-4499-886d-f83b8cd7eed2)

When configuring a scene where combat will occur, remember to set your Padding Percentage to maximum so that your players have room for their cards. I still recommend having a deck of cards for each player for organization, but you won’t need a separate hand of cards for each player, they’ll just put them on the canvas before the match begins.
You can use the default Drawing Tools to make a box or designate an area for each player if you like, at a minimum I would recommend a text box with the player’s name.
### USE
Each player deals their cards to the canvas at the start of combat. Click a Reaction card to flip it over. If one-time use cards, like some Reserves, are played, the GM can delete the Tile, or move it elsewhere.  The GM might also want to remove it from the player’s deck.

# Card Viewer
https://foundryvtt.com/packages/orcnog-card-viewer
### SYNOPSIS
This adds a convenient and attractive way to share cards with your players.  If you want to bring up any card as an on-screen object, click the card icon from the default foundry card stack. Next, click the Eye icon in the upper right corner to share it with your players.  Note that when a player performs this action, it sends a private message to the GM.  The GM can click the icon in this message to open the card themselves and share it as above.
As a side note, this module makes presenting new cards to players more fun and attractive.
