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
Containers: *No*
Is vital: **Yes**

### Muscles
Containers: *No*
Is vital: *No*

Physical strength

### Skeleton
Containers: *No*
Is vital: *No*

### Veins
Containers: **Blood** **Energy** **Hydration**
Is vital: **Yes**

They contain blood

### Lungs
Containers: **Air/Stamina**
Is vital: *No*

Allows executing more actions in short bursts

### Heart
Containers: *No*
Is vital: **Yes**

Keeps character alive

### Nerves
Containers: *No*
Is vital: **Yes**

### Stomach
Containers: **Digestible content**
Is vital: *No*

Every consumable has a weight value which goes into stomach. Stomach can not be overfilled or there will be negative side-effects if done so. There will be no penalty for empty stomach (unlike the original game).

### Uterus
Containers: **Fetus progress**
Is vital: *No*
Notes: **High-grade item**

Allows to spawn children based on it's and organism level(s)

## Skills/Perks
Each organ has it's own set of skills. Character starts with all skills at level 0 (hidden by default). Once unlocked levels goes up to 1 (of base level).
Actual level is calculated adding governed attribute, active effects and base level. *(formulae TBD)*

Skills level up as actions associated with them are executed *(debatable)*.
Actions fill experience bar of each corresponding skill.

As skill level increases various perks are unlocked.

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

**TODO:** We need to think about the way that these skills will be unlocked
**TODO:** Perks of skills unlock cost??

### Drinking
Organ: **Stomach**

Allows to use alcoholic drinks

#### Perks/Upgrades

##### Beer-man
Level: 5
Cost: *?*

Beer effects are 10% stronger

### Drugs
Organ: **Nerves**

Allows to use drugs

#### Perks/Upgrades

##### Filtered Intake
Level: 5
Cost: *?*

Lungs suffer 5% less when smoking

### Swimming
Organ: **Lungs**

(placeholder)

### Transplantation
Organ: **Brain**

Allows for transplantation of organs in the body

#### Perks/Upgrades

##### Organ Hot Swap
Level: 20
Cost: *?*

Transplantation side-effects are reduced by 10%

## Effects
All consumables when used are turned into effects. Same goes with actions that player does. Every effect has **description** of what it affects also **strength** and **duration**.

For example: `Restore Health 5 pts for 30 seconds`

When active this will restore players' health by 5 points of 30 seconds of game time.

Some effects might be permanent and might not have a duration (TBD)

#### Stacking same type of effects
Each effect type will have a flag if it is stack-able. If it's enabled many instances of the same effect can exist concurrently. If it is not enabled however overlapping effects might be dismissed or go into a queue until other ones expire (needs discussion)

## Consumables

### Food/Water
(all the foods ranging from sewage outlets to high quality ones)

### Drugs

#### Time passer drug (need a name)
"Character passes out"

Once taken, game immediately calculates game progress of x seconds and gives it to player.

## Addictions

Original game had chemical items that would yield higher gains for permanent damage effects. I think we should keep this to some extent while making benefits higher and also adding addictive effects.

Addictions would have many levels of depth, like there would be a very light addiction with very small withdrawal effects and if addiction where to progress those effects would become harsher. Of course progress shouldn't be crippled by this, unless corresponding drug is not used (withdrawal). Effectiveness should increase with addiction level too, meaning that player have "invest" into each addictive chemical. However player might use some additional "medicine" to slow down this level increase so to reduce withdrawal when not using.

Each addictive consumable would have an addiction counter, which would increase with use.

## Prestige system

While game will have a death where player looses progress, this mechanic will be merged with prestige system. Player comes back with reincarnation points that he will be able to add to his starting organs.

There are two ways that I'm thinking this:
* Upon death player chooses a scenario based on the points he's got
* Player restarts and after some time game offers a "dramatic life incidents" that will make those prestige points active

## Offline progress

A must. Though can be quite a challenge to implement considering all the processes happening at the same time that are dependant on each other.

If character simulation is impossible to calculate offline, we can suspend the character and keeps other processes running like investment and such. To player we can explain that the character goes into some sort of cryotank while offline. However I would avoid this all together if possible.

## Achievements

Complete x

Has unlocking order (dependency?)

**TODO:** What's for reward?

## Translations

Translations should change based on characters' state in-game. There should be a set of normal translations and also sets of state-specific translations that would override normal (if provided of course) in certain scenarios where this state counts as active.

*(example needed)*

## Tools

Game will support Web Workers through `.on(event, f: (data, ack))` and `.emit(event, data)` messaging system. That leaves a possibility to port into a game with server-side processing. *Or suggest a better solution*

```
webpack
vuejs
bootstrap-vue
typescript
tslint
rxjs
jest
lodash
sass
```
