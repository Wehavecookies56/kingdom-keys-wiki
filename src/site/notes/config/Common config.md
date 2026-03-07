---
{"dg-publish":true,"permalink":"/config/common-config/"}
---


Here you'll find some server options, those which do not need server enforcing them.

General:

|Name|Description|Default|Type|
|---|---|---|---|
|bombExplodeWithfire|Allow Bomb heartless to explode when lit on fire.|true|boolean|
|blizzardChangeBlocks|Allow Blizzard to turn lava into obsidian and freeze water.|true|boolean|
|keybladeOpenDoors|Allow keyblades to open iron doors with right click.|true|boolean|
|driveHeal|Health % restored when using a drive form.|50|integer (0-100)|
|critMult|Critical Damage Multiplier.|1.5|double (0-100)|
|needKeybladeForHeartless|Force the player to need a Keyblade or an Organization weapon to hurt Heartless and Nobodies.|false|boolean|

Gummi:

|Name|Description|Default|Type|
|---|---|---|---|
|allowBlocksInHangarArea|Allow the player to place a hangar in a zone where there are blocks already (probably a good idea to disable on servers).|true|boolean|
|gummiBlocksDropPercent|Percentage of blocks dropped when the Gummi Ship gets destroyed.|80|integer (0-100)|

Savepoint:

| Name                       | Description                                                                           | Default                                                                                                                                                                                                | Type   |
| -------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------ |
| savePointMaterials         | Materials used to upgrade save points. Format: `STAT=item`.                           | HP=kingdomkeys:orichalcum,MP=kingdomkeys:illusory_crystal,HUNGER=kingdomkeys:hungry_crystal,FOCUS=kingdomkeys:remembrance_crystal,DRIVE=kingdomkeys:evanescent_crystal,TIER=kingdomkeys:orichalcumplus | string |
| normalSavePointRestoreList | Stats restored when using a normal savepoint (Allowed: HP, MP, HUNGER, FOCUS, DRIVE). | HP,MP                                                                                                                                                                                                  | string |
| fullSavePointRestoreList   | Stats restored when using a linked savepoint.                                         | HP,HUNGER,MP,FOCUS                                                                                                                                                                                     | string |
| warpPointRestoreList       | Stats restored when using a warp point.                                               | HP,HUNGER,MP,FOCUS,DRIVE                                                                                                                                                                               | string |

Drops:

|Name|Description|Default|Type|
|---|---|---|---|
|hpDropProbability|HP Drops Probability.|80|integer (0-100)|
|mpDropProbability|MP Drops Probability.|80|integer (0-100)|
|munnyDropProbability|Munny Drops Probability.|80|integer (0-100)|
|driveDropProbability|Drive Drops Probability.|80|integer (0-100)|
|focusDropProbability|Focus Drops Probability.|80|integer (0-100)|
|drivePointsMultiplier|Drive Points Drop Multiplier.|1.0|float (0-100)|
|focusPointsMultiplier|Focus Points Drop Multiplier.|1.0|float (0-100)|

Recipes:

|Name|Description|Default|Type|
|---|---|---|---|
|recipeDropChance|Recipe drop chance.|2|integer (0-100)|

Spawning:

|Name|Description|Default|Type|
|---|---|---|---|
|heartlessSpawningMode|Heartless spawning mode: NEVER, ALWAYS, AFTER_KEYCHAIN, AFTER_DRAGON.|AFTER_KEYCHAIN|enum|
|mobSpawn|Mob spawn chance list `[type, chance]`.|["Pureblood,35","Emblem,35","Nobody,30"]|list|
|playerSpawnHeartless|Allow a heartless and a nobody to spawn when a player gets killed by a heartless.|true|boolean|
|mobLevelingUp|Allow heartless and nobodies to spawn with levels according to players.|true|boolean|
|mobLevelName|Add the level to the name of mobs.|true|boolean|
|rodHeartlessLevelScale|Heartless spawning in the Realm of Darkness will increase 1 level every X blocks.|10|integer (1-1000)|
|rodHeartlessMaxLevel|Max level for heartless spawning in Realm of Darkness.|200|integer (1-10000)|
|playerSpawnHeartlessData|Heartless and nobody stats: `name, hp (% of player), strength (% of player)`.|["Heartless,100,100","Nobody,100,100"]|list|
|respawnROD|Force players who die in the Realm of Darkness to respawn there.|false|boolean|
|mobLevelStats|Mob base stats multiplier out of 100%.|10|integer (0-100)|
|bossDespawnIfNoTarget|Make bosses despawn once their target disappears.|true|boolean|

Shotlock:

|Name|Description|Default|Type|
|---|---|---|---|
|shotlockMult|Shotlock Damage Multiplier (magic * multiplier).|0.4|float (0-100)|

Synthesis:

| Name            | Description                                          | Default                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Type |
| --------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---- |
| startingRecipes | Synthesis recipes given to the player on first join. | ["kingdomkeys:mythril_shard", "kingdomkeys:mythril_stone", "kingdomkeys:mythril_gem", "kingdomkeys:mythril_crystal", "kingdomkeys:potion", "kingdomkeys:hi_potion", "kingdomkeys:mega_potion", "kingdomkeys:ether", "kingdomkeys:hi_ether", "kingdomkeys:mega_ether", "kingdomkeys:elixir", "kingdomkeys:mega_lixir", "kingdomkeys:drive_recovery", "kingdomkeys:hi_drive_recovery", "kingdomkeys:refocuser", "kingdomkeys:hi_refocuser", "kingdomkeys:powerboost", "kingdomkeys:magicboost", "kingdomkeys:defenseboost", "kingdomkeys:apboost"] | list |


