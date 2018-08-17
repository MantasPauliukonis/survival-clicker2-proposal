# survival-clicker2-proposal

## Intro

To completely understand the following please check the original game if you haven't already done so.

Everything that is written here is meant to re-iterate and improve on the original idea that will later be turned into an operational game (fingers crossed).

Please suggest more creative names for things! I'm really bad at this :)

**Please discuss before making any pull requests.**

[Play the original game here](http://survival.clicker.7777.lt)

## Stats

### Money
(WIP)

## Organs

They are vital! Well at least most of them.

Organs are optional and some of them are only unlocked at some later time in game.

Organ performance can be boosted with effects (from consumables or what have you), but can not be permanently increased (talking about organ level) with once exception: *See: Prestige system*

Organs can be bought and transplanted, Character could have more instances of the same organ (later game)

#### Variables

`Organ level` - level of the organ

`Maximum health` - Determines maximum health value of the organ, deteriorates over time and can not be restored (organ must be transplanted). Starting value is based on organ level

`Current health` - current health of the organ, impacts function performance

If organ has a container(s): *(Open to discussion)*

`Container name` - example: for veins it's blood and for lungs it's air

`Container size` - Maximum amount of *stuff* that can be added (ex. stomach - food, veins - blood, lungs - air and etc.). Starting container size is based of organ level

`Container used` - Amount of *stuff* currently in container

### Brain
Is container: *No*
Is vital: **Yes**

### Muscles
Is container: *No*
Is vital: *No*

Physical strength

### Skeleton
Is container: *No*
Is vital: *No*

### Veins
Is container: **Yes**
Is vital: **Yes**

They contain blood

### Lungs
Is container: **Yes**
Is vital: *No*

Allows executing more actions in short bursts

### Heart
Is container: *No*
Is vital: **Yes**

Keeps character alive

### Nerves
Is container: *No*
Is vital: **Yes**

### Stomach
Is container: **Yes**
Is vital: *No*

Every consumable has a weight value which goes into stomach. Stomach can not be overfilled or there will be negative side-effects if done so. There will be no penalty for empty stomach (unlike the original game).

### Uterus
Is container: *No*
Is vital: *No*
Notes: **High-grade item**

Allows to spawn children based on it's and organism level(s)

## Skills/Perks
Each attribute has it's own set of skills. Character starts with all skills at level 0. Once unlocked levels goes up to 1 (of base level).
Actual level is calculated adding governed attribute, active effects and base level. (formulae TBD)

Skills level up as actions associated with them are executed (debatable).
Actions fill experience bar on each skill.

Experience needed for next level is calculated using: 
`baseExperience * 1.2^(currentLevel - 1)`

with `baseExperience` of `100`

Level|Experience
---|---
1|100
2|120
3|144
5|207~
10|516~
25|7950~
50|758K~

We also need to think about sub-skills or perks that would add additional benefits (imagine like upgrades in other incremental games)

### Drinking
Organ: **Stomach**

Yield more positive and less negative effects of alcohol

### Chem-Taker
Organ: **Nerves**

Yield more positive and less negative effects of suspicious chemicals and drugs

### Swimming
Organ: **Lungs**

(placeholder)

## Effects
All consumables when used are turned into effects. Same goes with actions that player does. Every effect has **description** of what it affects also **strength** and **duration**.

For example: `Restore Health 5 pts for 30 seconds`

When active this will restore players' health by 5 points of 30 seconds of game time.

Some effects might be permanent and might not have a duration (TBD)

#### Stacking same type of effects
Each effect type will have a flag if it is stack-able. If it's enabled many instances of the same effect can exist concurrently. If it is not enabled however overlapping effects might be dismissed or go into a queue until other ones expire (needs discussion)

## Consumables

### Drugs

#### Time passer drug (need a name)
"Character passes out"

Once taken, game immediately calculates game progress of x seconds and gives it to player.

## Addictions
Original game had chemical items that would yield higher gains for permanent damage effects. I think we should keep this to some extent while making benefits higher and also adding addictive effects.

Addictions would have many levels of depth, like there would be a very light addiction with very small withdrawal effects and if addiction where to progress those effects would become harsher. Of course progress shouldn't be crippled by this, unless corresponding drug is not used (withdrawal)

## Prestige system

While game will have a death where player looses progress, this mechanic will be merged with prestige system. Player comes back with reincarnation points that he will be able to add to his attributes.

## Offline progress

A must. Though can be quite a challenge to implement considering all processes happening at the same time dependant on each other.

If character simulation is impossible to calculate offline, we can suspend the character and keeps other processes running like investment and such. To player we can explain that the character goes into some sort of cryotank while offline. However I would avoid this all together if possible.

## Tools

Game will support Web Workers through `.on(event, f: (data, ack))` and `.emit(event, data)` messaging system. That leaves a possibility to port into a game with server-side processing.

```
webpack
vuejs
bootstrap-vue
typescript
tslint
rxjs
jest
lodash
```
