---
{"dg-publish":true,"permalink":"/config/server-config/"}
---


Here you'll find some server options, those which do need server enforcing them.

General

| Name                | Description                                                                                                                                                                                                                                   | Default | Type             |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ---------------- |
| softLockOnMode      | Soft lock on allows you to move the camera as long as you keep the locked entity visible on the screen.<br>Disabling this will enforce the old hard lock on which wouldn't allow the camera to be moved at all while an entity was locked on. | true    | boolean          |
| gummiShipFuelSystem | Set whether to enable Gummi Ships fuel system.                                                                                                                                                                                                | true    | boolean          |
| finalMixVariantChance | Percentage chance for a spawning Heartless to use its Final Mix palette variant.                                                                                                                                                            | 10      | integer (0-100)  |
| partyRangeLimit     | Party range limit.                                                                                                                                                                                                                            | 50      | integer (1-150)  |
| partyMembersLimit   | Party members limit.                                                                                                                                                                                                                          | 5       | integer (1-20)   |
| requireSynthTier    | If true players will only be able to synthesis items from their tier or lower, if false they can synthesise all regardless of their tier.                                                                                                     | false   | boolean          |
| requireSynthTierShop | If true players will only be able to buy items from their tier or lower, if false they can buy all of them regardless of their tier.                                                                                                        | true    | boolean          |
| requireMeldingTier  | If true players will only be able to meld commands from their tier or lower, if false they can meld all of them regardless of their tier.                                                                                                     | true    | boolean          |
| projectorHasShop    | If true moogle projectors will have the default shop available, if false only the moogles will.                                                                                                                                               | false   | boolean          |
| savepointGlobal     | If true savepoints will allow any player to mark it as global, if false only creative players will.                                                                                                                                           | false   | boolean          |
| getExpFromShop      | If true both synthesis and moogle shop will give EXP for recipes, if false only synthesis.                                                                                                                                                    | false   | boolean          |
| orgEnabled          | If true the organization system will be enabled, if false will be disabled.                                                                                                                                                                   | true    | boolean          |
| allowBoosts         | If true then boosts like Power Boost, Magic Boost and Defense Boost will be enabled, if false they won't add stats.                                                                                                                           | true    | boolean          |
| allowPartyKO        | If true then when a player in a party (with more party members online) dies, they will be put in a KO state allowing to cast cure or potions to be revived. If Supplementaries is installed, set `send_chat_on_death = false` in `supplementaries-client.toml` to avoid issues. | true    | boolean          |
| wayfinderCD         | Cooldown (in seconds) for the Wayfinder after a successful teleport.                                                                                                                                                                           | 300     | integer (1-10000) |
| wayfinderCDCall     | Cooldown (in seconds) for the Wayfinder after a call.                                                                                                                                                                                          | 30      | integer (1-10000) |
| wayfinderParty      | If true then players will only be able to use the Wayfinder with other party members, if false with anyone.                                                                                                                                   | true    | boolean          |
| hostileMobsLevel    | If true other hostile mobs will level up alongside the player level the same way heartless do.                                                                                                                                                | true    | boolean          |
| dragonLevel         | If true the Enderdragon will level up too.                                                                                                                                                                                                     | true    | boolean          |
| shotlockMaxDist     | Shotlock max distance for locking.                                                                                                                                                                                                            | 200     | integer (1-1000) |
| allowCastMagicIfTooExpensive | If true it will allow you to cast a magic which is too expensive even if you don't have the required Max MP (e.g. Stop at level 4).                                                                                                 | true    | boolean          |
| perMagicCooldown    | If true each magic has its own cooldown, so casting one does not lock the rest (Birth by Sleep style). If false a single shared cooldown blocks every magic.                                                                                   | false   | boolean          |
| perMagicCooldownMultiplier | Multiplies magic cooldowns while perMagicCooldown is on.                                                                                                                                                                                | 4.0     | double (0.1-100) |
| shotlockMinigames   | If true, landing a full Shotlock with a level 2+ Shotlock item starts a follow-up minigame (mash, timing ring or WASD prompts).                                                                                                               | true    | boolean          |
| allowAllOrgLimits   | If true it will allow any Organization XIII member to use any limit, if false only the associated member ones.                                                                                                                                | false   | boolean          |


Leveling

| Name                  | Description                                                                           | Default                                               | Type           |
| --------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------------- | -------------- |
| xpMultiplier          | XP multiplier.                                                                        | 1.0                                                   | float (0-1000) |
| magicXPMultiplier     | Magic spells XP multiplier.                                                           | 0.4                                                   | float (0-1000) |
| heartMultiplier       | Hearts multiplier.                                                                    | 1.0                                                   | float (0-1000) |
| partyXPShare          | XP share in party (killer gets 100%, the rest of party members the % specified here). | 0.0                                                   | float (0-100)  |
| driveFormXPMultiplier | Drive Form XP multipliers defined per form in format `FormName,Multiplier`.           | ["Valor,1","Wisdom,1","Limit,1","Master,1","Final,1"] | list           |
| statsMultiplier       | Strength, Magic and Defense multiplier in % for players.                              | [100,100,100]                                         | list           |



