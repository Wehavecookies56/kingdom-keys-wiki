---
{"dg-publish":true,"permalink":"/config/common-config/"}
---


Here you'll find some server options, those which do not need server enforcing them.

General:



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| bombExplodeWithfire | Allow Bomb heartless to explode when lit on fire. | true | boolean |
| keybladeOpenDoors | Allow keyblades to open iron doors with right click. | true | boolean |
| driveHeal | Health % restored when using a drive form. | 50 | integer (0-100) |
| critMult | Critical Damage Multiplier. | 1.5 | double (0.0-100.0) |
| needKeybladeForHeartless | Force the player to need a Keyblade or an Organization weapon to hurt Heartless, and Nobodies. | false | boolean |
| hideOrgNames | When enabled players wearing the whole Organization XIII set will not show their playername on their head and in the Tab menu. | true | boolean |
| generateCOEntrance | Generates the structure to enter Castle Oblivion. | true | boolean |
| coEntranceChunkX | Chunk X coord to generate Castle Oblivion entrance. | 13 | integer (0-1000) |
| coEntranceChunkZ | Chunk Z coord to generate Castle Oblivion entrance. | 7 | integer (0-1000) |



Gummi:



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| allowBlocksInHangarArea | Allow the player to place a hangar in a zone where there are blocks already (probably a good idea to disable on servers). | true | boolean |
| gummiBlocksDropPercent | Percentage of blocks dropped when the Gummi Ship gets destroyed. | 80 | integer (0-100) |
| fuelConsumeFactor | Factor of fuel consumption, the higher the more it consumes. | 0.1 | double (0.0-100.0) |



>[!info] Savepoints
>Savepoint upgrade materials and which stats each tier (normal/linked/warp) restores are no longer set here. They're now data-driven via datapack JSON files at `data/kingdomkeys/savepoints/normal.json`, `linked.json` and `warp.json`, which server owners can override with a datapack. See [[data-driven customization/Savepoint Data\|Savepoint Data]].

Drops: (includes the recipe drop chances too, they live in the same `drops` config block as the other drop rates)



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| hpDropProbability | HP Drops Probability. | 80 | integer (0-100) |
| mpDropProbability | MP Drops Probability. | 80 | integer (0-100) |
| munnyDropProbability | Munny Drops Probability. | 80 | integer (0-100) |
| driveDropProbability | Drive Drops Probability. | 80 | integer (0-100) |
| focusDropProbability | Focus Drops Probability. | 80 | integer (0-100) |
| drivePointsMultiplier | Drive Points Drop Multiplier. | 1.0 | double (0.0-100.0) |
| focusPointsMultiplier | Focus Points Drop Multiplier. | 1.0 | double (0.0-100.0) |
| recipeDropChance | Recipe drop chance. | 2 | integer (0-100) |
| biomeMemoryDropChance | Biome Memory drop chance. | 1 | integer (0-100) |



Spawning:



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| heartlessSpawningMode | Heartless spawning mode: NEVER, ALWAYS, AFTER_KEYCHAIN (after the first keychain is synthesized), AFTER_DRAGON (after the Ender Dragon is defeated). | AFTER_KEYCHAIN | enum |
| mobSpawn | Mob Spawn chance in percentage [type, chance] (if the chance doesn't add up to 100, enemies will not spawn). | ["Pureblood,35", "Emblem,35", "Nobody,30"] | list |
| playerSpawnHeartless | Allow a heartless and a nobody to spawn when a player gets killed by a heartless. | true | boolean |
| mobLevelingUp | Allow heartless and nobodies to spawn with levels according to players. | true | boolean |
| mobLevelName | Add the level to the name of mobs, when this is enabled the name will not be removed from mobs that have already spawned in your world. | true | boolean |
| rodHeartlessLevelScale | Heartless spawning in the ROD will increase 1 level every X blocks. | 10 | integer (1-1000) |
| rodHeartlessMaxLevel | Max level for heartless spawning in ROD. | 200 | integer (1-10000) |
| playerSpawnHeartlessData | Heartless and nobody stats: name, hp (% of the player's), strength (% of the player's). | ["Heartless,100,100", "Nobody,100,100"] | list |
| respawnROD | Force players who die in the Realm of Darkness to respawn there. | false | boolean |
| mobLevelStats | Mob base stats multiplier out of 100% (default 10). | 10 | integer (0-100) |
| bossDespawnIfNoTarget | Make bosses despawn once his target disappears. | true | boolean |



Shotlock:



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| shotlockMult | Shotlock Damage Multiplier (magic * multiplier). | 0.4 | double (0.0-100.0) |



Synthesis:



| Name | Description | Default | Type |
| --- | --- | --- | --- |
| startingRecipes | Synthesis recipes given to the player on first join, so changing this list will not give you recipes in worlds you've already created. | ["kingdomkeys:kingdom_key", "kingdomkeys:mythril_shard", "kingdomkeys:mythril_stone", "kingdomkeys:mythril_gem", "kingdomkeys:mythril_crystal", "kingdomkeys:potion", "kingdomkeys:hi_potion", "kingdomkeys:mega_potion", "kingdomkeys:ether", "kingdomkeys:hi_ether", "kingdomkeys:mega_ether", "kingdomkeys:elixir", "kingdomkeys:mega_lixir", "kingdomkeys:drive_recovery", "kingdomkeys:hi_drive_recovery", "kingdomkeys:refocuser", "kingdomkeys:hi_refocuser", "kingdomkeys:powerboost", "kingdomkeys:magicboost", "kingdomkeys:defenseboost", "kingdomkeys:apboost"] | list |


