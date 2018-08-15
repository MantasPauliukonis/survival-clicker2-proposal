# survival-clicker2-proposal

## Intro

To completely understand the following please check the original game if you haven't already done so.

Everything that is written here is meant to re-iterate and improve on the original idea that will later be turned into an operational game (fingers crossed).

Please discuss before making any pull requests.

[Play the original game here](http://survival.clicker.7777.lt)

## Stats

### Stomach
Every consumable has a weight value which goes into stomach. Stomach can not be overfilled or there will be negative side-effects if done so. There will be no penalty for empty stomach (like in original game).

### Stamina
Every action will drain stamina, more intense action is more stamina it will drain.

## Attributes
Number higher than 1, most likely to go to infinity.

### Strength
Defines how strong the character is.

#### Skills/Perks
Each attribute has it's own set of perks. Character starts with all perks at level 0. Once unlocked levels goes up to 1.
Perks level up as actions associated with them are executed (debatable).

##### Swimming
(placeholder)

## Effects
All consumables when used are turned into effects. Same goes with actions that player does. Every effect has **description** of what it affects also **strength** and **duration**.

For example: `Restore Health 5 pts for 30 seconds`

When active this will restore players' health by 5 points of 30 seconds of game time.

Some effects might be permanent and might not have a duration (TBD)

#### Stacking same type of effects
~~When adding new effects to characters effect list if same type is encountered, strength will be averaged out based on duration.~~
Stacking effects might be overpowered, looking for a solution...

## Prestige system

While game will have a death where player looses progress, this mechanic will be merged with prestige system. Means that player will come back with some additional bonus (TBD)

## Tools
```
webpack
vuejs
bootstrap-vue
typescript
tslint
```
