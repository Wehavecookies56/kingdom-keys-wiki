---
{"dg-publish":true,"permalink":"/config/server-config/"}
---


Here you'll find some server options, those which do need server enforcing them.

General

| Name                | Description                                                                                                                                                                                                                                   | Default | Type             |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ---------------- |
| softLockOnMode      | Soft lock on allows you to move the camera as long as you keep the locked entity visible on the screen.<br>Disabling this will enforce the old hard lock on which wouldn't allow the camera to be moved at all while an entity was locked on. | true    | boolean          |
| gummiShipFuelSystem | Set whether to enable Gummi Ships fuel system.                                                                                                                                                                                                | true    | boolean          |
| partyRangeLimit     | Party range limit.                                                                                                                                                                                                                            | 50      | integer (1-150)  |
| partyMembersLimit   | Party members limit.                                                                                                                                                                                                                          | 5       | integer (1-20)   |
| requireSynthTier    | If true players will only be able to synthesis items from their tier or lower, if false they can synthesise all regardless of their tier.                                                                                                     | false   | boolean          |
| projectorHasShop    | If true moogle projectors will have the default shop available, if false only the moogles will.                                                                                                                                               | false   | boolean          |
| getExpFromShop      | If true both synthesis and moogle shop will give EXP for recipes, if false only synthesis.                                                                                                                                                    | false   | boolean          |
| orgEnabled          | If true the organization system will be enabled, if false will be disabled.                                                                                                                                                                   | true    | boolean          |
| allowBoosts         | If true then boosts like Power Boost, Magic Boost and Defense Boost will be enabled, if false they won't add stats.                                                                                                                           | true    | boolean          |
| allowPartyKO        | If true then when a player in a party (with more party members online) dies, they will be put in a KO state allowing to cast cure or potions to be revived.                                                                                   | true    | boolean          |
| wayfinderParty      | If true then players will only be able to use the Wayfinder with other party members, if false with anyone.                                                                                                                                   | true    | boolean          |
| hostileMobsLevel    | If true other hostile mobs will level up alongside the player level the same way heartless do.                                                                                                                                                | true    | boolean          |
| shotlockMaxDist     | Shotlock max distance for locking.                                                                                                                                                                                                            | 200     | integer (1-1000) |


Leveling

| Name                  | Description                                                                           | Default                                               | Type           |
| --------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------- | -------------- |
| xpMultiplier          | XP multiplier.                                                                        | 1.0                                                   | float (0-1000) |
| heartMultiplier       | Hearts multiplier.                                                                    | 1.0                                                   | float (0-1000) |
| partyXPShare          | XP share in party (killer gets 100%, the rest of party members the % specified here). | 0.0                                                   | float (0-100)  |
| driveFormXPMultiplier | Drive Form XP multipliers defined per form in format `FormName,Multiplier`.           | ["Valor,1","Wisdom,1","Limit,1","Master,1","Final,1"] | list           |
| statsMultiplier       | Strength, Magic and Defense multiplier in % for players.                              | [100,100,100]                                         | list           |



