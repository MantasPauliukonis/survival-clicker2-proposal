# survival-clicker2-proposal

## Intro

To completely understand the following please check the original game if you haven't already done so.

Everything that is written here is meant to re-iterate and improve on the original idea that will later be turned into an operational game (fingers crossed).

Please suggest more creative names for things! I'm really bad at this :)

**Please discuss before making any pull requests.**

[Play the original game here](http://survival.clicker.7777.lt)

## Stats

### Money

### Health
Starting capacity is governed by **Endurance** attribute.

### Stomach
Starting capacity is governed by **Endurance** attribute.

Every consumable has a weight value which goes into stomach. Stomach can not be overfilled or there will be negative side-effects if done so. There will be no penalty for empty stomach (unlike the original game).

### Stamina
Starting capacity is governed by **Strength** attribute.

Every action will drain stamina, more intense action is more stamina it will drain.

## Attributes
Number higher than 1, most likely to go to infinity.

Attributes can be boosted with effects (from consumables or what have you), but can not be permanently increased with once exception: _See: Prestige system_

### Strength
Defines how strong the character is.

### Mentality
Mental strength, ability to fight addiction and depression

### Intelligence
IQ

### Personality
Ability to communicate with external world

### Endurance
Survive more abuse in one go.

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
Parent attribute: **Mentality**

Yield more positive and less negative effects of alcohol

### Chem-Taker
Parent attribute: **Mentality**

Yield more positive and less negative effects of suspicious chemicals and drugs

### Swimming
Parent attribute: **Strength**

(placeholder)

## Effects
All consumables when used are turned into effects. Same goes with actions that player does. Every effect has **description** of what it affects also **strength** and **duration**.

For example: `Restore Health 5 pts for 30 seconds`

When active this will restore players' health by 5 points of 30 seconds of game time.

Some effects might be permanent and might not have a duration (TBD)

#### Stacking same type of effects
Each effect type will have a flag if it is stack-able. If it's enabled many instances of the same effect can exist concurrently. If it is not enabled however (spinning gears)

## Addictions
Original game had chemical items that would yield higher gains for permanent damage effects. I think we should keep this to some extent while making benefits higher and also adding addictive effects.

Addictions would have many levels of depth, like there would be a very light addiction with very small withdrawal effects and if addiction where to progress those effects would become harsher. Of course progress shouldn't be crippled by this, unless corresponding drug is not used (withdrawal)

## Prestige system

While game will have a death where player looses progress, this mechanic will be merged with prestige system. Player comes back with reincarnation points that he will be able to add to his attributes.

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
