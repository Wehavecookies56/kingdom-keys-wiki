---
{"dg-publish":true,"permalink":"/config/castle-oblivion-data/"}
---

[[Systems/Castle Oblivion\|Castle Oblivion]] is highly customisable through datapacks with 4 different types of JSON files as well as making use of tags and `.nbt` structure files. 

Castle Oblivion is comprised of Floors and those Floors contains Rooms each Floor has a FloorType and each Room has a RoomType these types contain immutable information read from the JSON files when a Room is generated a structure is chosen structure has to be compatible with the RoomType from the card used as well as the FloorType of the current Floor the selected structure is represented by a RoomStructure which defines properties to check compatibility as well as which structure file to actually generate. Within the Floors there are special rooms that require a keycard to enter and upon entering will start an Encounter these encounters are defined in the RoomEncounters. Rooms, Floors and Wave Encounters all have a modifier field in the JSONs these are special effects that can apply every tick or when a room is entered, when a room is exited, when a room is generated and when a mob spawns. As these are quite complex these will get their own section explaining them.

# Floor Type
Floor Types define properties of a floor acting as a parent for Room Types.

Floor Type JSONs are in the `castle_oblivion/floor_type` folder. It is possible to add new Floor Types however adding a new card that uses that type is currently not, a simple addon mod would need to be created to add a new card item.
Here is a breakdown of the JSON file structure:
* `(int) crit_path_length`: When generating the floor it generates a "crit path" which is the main path of rooms from the entrance this value determines how many rooms to generate.
* `(string) biome_colours`: The biome to get the colours for the grass, water, foliage and sky colour from for the rooms on this floor. The sky colour is used for the wall colours unless `use_fog_colour` is true or if a [[#Room Type]] overrides it
* `[optional] (string) music`: The music to play while in the rooms can be overridden by the [[#Room Type]]
* `[optional] (array string) room_blacklist` A list of rooms to blacklist from generating for this floor. This isn't fully implemented yet.
* `[optional] (string) starting_room` The first room generated when using the world card in the entrance hall by default this is `kingdomkeys:unknown_room`
* `[optional] (array modifier) modifiers`: The modifiers for the room see [[#Room Modifier]] for how these work
* `[optional] (tag string) regular_enemies`: The tag for the enemy spawning pool if this is not set the default tag `\#kingdomkeys:castle_oblivion/regular_enemies` is used. This can be overridden by the [[#Room Type]].
* `[optional] (tag string) strong_enemies`: Currently not implemented
* `[optional] (bool) use_fog_colour`: Use the fog colour from the biome specified in `biome_colours` instead of the sky colour for the room wall colours this is useful for biomes that don't use the sky colour usually like Nether Wastes which has blue sky but red fog.

> [!example] Example: plains.json
> ```json
> {  
>  "biome_colours": "minecraft:plains",  
>  "crit_path_length": 7,  
>  "music": "minecraft:music.game"  
>}
> ```

# Room Type
Room Types define properties for Rooms used for generating the rooms.

Room Type JSONs are in the `castle_oblivion/room_type` folder. It is possible to add new Room Types however adding a new card that uses that type is currently not, a simple addon mod would need to be created to add a new card item.
Here is a breakdown of the JSON file structure:
* `(enum string) size`: This is simply the size classification of the room. Only RoomStructures with a matching size will be compatible. Possible values are "SPECIAL", "S", "M", "L"
*  `(enum string) category`: This is the category of the Room Type used for finding compatible structures. Possible values are "ENEMY", "STATUS", "BOUNTY" "SPECIAL", "ENCOUNTER", "ANY"
* `[optional] (object) enemies`:  This contains the properties for rooms that have random enemy spawns
	*  `(enum string) type`: This is used to display the stars on the cards. Possible values "NONE", "S", "M", "L"
	* `(integer) number_of_enemies`: This is the total number of enemies that can spawn in the room
	* `(integer) simultaneous_enemies`: This is how many enemies can be spawned at a time in the room if this value is greater than or equal to `number_of_enemies` it is effectively ignored.
	* `[optional] (tag string) regular_enemies`: The tag for the enemy spawning pool if this is not set `regular_enemies` from the [[#Floor Type]] is used.
	* `[optional] (tag string) strong_enemies`: Currently not implemented
* `[optional] (bool) entrance_hall`: Marks whether the room type is an entrance hall should really only be used by the entrance hall room type
* `[optional] (hex string) colour`: The hex colour for the colour of the room's walls if this is not set the FloorType wall colour is used
* `[optional] (array modifier) modifiers`: The modifiers for the room see [[#Room Modifier]] for how these work
* `[optional] (array string) compatible`: The [[#Floor Type]] this room is compatible with should be an existing floor type such as `kingdomkeys:plains`.
* `[optional] (string) fixed_room`: Specifies a specific room structure this room type should generate rather than getting a random compatible structure
* `[optional] (string) music`: Music to play while the player is inside the room
* `[optional] (string) encounter`: The [[#Room Encounter]] for the room

> [!example] Example: stagnant_space.json
> ```json
> {
>  "category": "STATUS",
>  "enemies": {
>    "type": "S",
>    "number_of_enemies": 5,
>    "simultaneous_enemies": 3
>  },
>  "modifiers": [
>    {
>      "type": "kingdomkeys:effect",
>      "amplifier": 0,
>      "effect": "minecraft:slowness",
>      "target": "MOB"
>    }
>  ],
>  "size": "M"
>}
> ```

# Room Structure
Room Structures link the `.nbt` structure files with the room generation defining the properties of a the structures so compatibility can be checked with the Room Type.

Room Structure JSONs are in the `castle_oblivion/room_structure`.
Here is a breakdown of the JSON file structure:
* `(string) structure`: The file name for the structure if `floor_specific_structure` is true then the generator will load a structure with this file name in the folder for the current floor otherwise it will load from the `all` folder. So for example `kingdomkeys:small_1` has `"structure": "small_1"` if you are on a plains floor it will generate `data\kingdomkeys\structure\castle_oblivion\rooms\plains\small_1.nbt`
* `(enum string) size`: The size categorisation of the room, the with and depth should be around 32x32 for S, 48x48 for M and 64x64 for L. SPECIAL is used for room such as the Entrance Hall where the size doesn't matter and generally shouldn't be used for normal rooms. Possible values are "SPECIAL", "S", "M", "L"
* `(enum string array) categories`: This is a list of the compatible categories of [[#Room Type]] . Possible values are "ENEMY", "STATUS", "BOUNTY" "SPECIAL", "ENCOUNTER", "ANY".
* `[optional] (bool) floor_specific_structure`: Setting this to false means the structure will be loaded from the "all" folder 

>[!example] Example: moogle_room.json
> ```json
> {  
>  "categories": [  
>    "BOUNTY"  
>  ],  
>  "size": "S",  
>  "structure": "moogle_room",  
>  "white_list": [  
>    "kingdomkeys:moogle_room"  
>  ]  
>}
> ```
# Room Encounter
Room Encounters are encounters that initiate in a room and then end whenever the type of encounter's end condition is met. The main part of a Room Encounter is the Encounter type, depending on the type of encounter the JSON options will change. The other option is the list of items to give as rewards for completing the encounter.

Room Encounter JSONs are in the `castle_oblivion/room_encounter` custom ones can simply be made by making a new file and setting the encounter for a [[#Room Type]] with the new encounter.
Here is a breakdown of the JSON file structure:
* `(object) encounter`:  The definition for the encounter
	* `(string) type`: The type of encounter this determines the rest of the options for the encounter see [[#Encounter Types]].
* `(object array) rewards`: List of items to give when the encounter has completed these can have components and a count, can be empty.
* `[optional] (string) music`: Music to play while the encounter is active

> [!example] Example: room_of_beginnings.json
> ```json
>{  
>  "encounter": {  
>    "type": "kingdomkeys:wave",
>    ...  
>  },  
>  "music": "kingdomkeys:music/forgotten_challenge",  
>  "rewards": [  
>    {  
>      "count": 1,  
>      "id": "kingdomkeys:key_of_guidance"  
>    }  
>  ]  
>}
> ```

## Encounter Types
Encounter Types have options specific to the type of encounter they are so the JSON structure is different for each one. There is currently only 1 type, more are planned for the future. 
### Wave
Wave encounters are what they sound like when the encounter starts the first wave of enemies are spawned and then when all of them have died the next wave spawns until the final wave. Once the final wave is defeated the encounter is completed.

Here is a breakdown of the JSON structure for type `kingdomkeys:wave`
* `(int) interval_ticks`: Currently not implemented so value does nothing right now however it is required.
* `[optional] (bool) shuffle_order`: Randomises the order the waves spawn in by default it follows the order they're defined.
* `(object array) waves`: The list of waves
	* `(string array) spawns`: The list of entities to spawn for the wave
	* `[optional] (modifier array) modifiers`:  The modifiers for the wave see [[#Room Modifier]] for how these work. Modifiers that do something when the room is generated will not do anything.

> [!example] Example: room_of_beginnings.json
> ```json
> "type": "kingdomkeys:wave",  
>"interval_ticks": 100,  
>"shuffle_order": false,  
>"waves": [  
 > {  
>    "modifiers": [],  
>    "spawns": [  
>      "kingdomkeys:shadow",  
>      "kingdomkeys:shadow",  
>      "kingdomkeys:shadow"  
>    ]  
>  },  
>  {  
>    "modifiers": [],  
>    "spawns": [  
>      "kingdomkeys:red_nocturne",  
>      "kingdomkeys:blue_rhapsody",  
>      "kingdomkeys:shadow"  
>    ]  
>  },  
>  {  
>    "modifiers": [],  
>    "spawns": [  
>      "kingdomkeys:shadow",  
>      "kingdomkeys:soldier",  
>      "kingdomkeys:shadow"  
>    ]  
>  }  
>]
> ```
# Room Modifier
Room Modifiers are quite versatile objects that can be added to a [[#Room Type]], [[#Floor Type]] and [[#Wave]] Encounters. They can do things when a room is entered and exited, every tick while players are in a room, when a room is generated and when a mob spawns in a room. Each type of modifier has its own options for the JSON.
## Effect
The effect type `kingdomkeys:effect` applies an effect with infinite duration to players and mobs depending on the target set while in the room.
Here is a breakdown of the JSON structure:
* `(string) effect`: The effect to apply.
* `[optional] (int) amplifier`: The level of the effect. 0 by default.
* `(enum string) target`: Whether to target players, mobs or both. Possible values "PLAYER", "MOB", "BOTH" 

> [!example] Example: bottomless_darkness.json
> ```json
> "modifiers": [  
>  {  
>    "type": "kingdomkeys:effect",  
>    "amplifier": 0,  
>    "effect": "minecraft:darkness",  
>    "target": "PLAYER"  
>  }  
>]
> ```
> This applies the darkness effect to players while in the room
## Level
The level type `kingdomkeys:level` modifies the level mobs spawn at applying the supplied operations in order. The base value will be the floor number multiplied by 10 then +/- 3.
The `+` operator performs value + amount.
The `-` operator performs value - amount.
The `*` operator performs value \* amount.
The `=` operator performs value = amount, if used it should be first in the list as any operations performed before will be redundant.
The `rand` operator performs value + random value between -amount and amount.
Here is a breakdown of the JSON structure:
* `(object array) operations`: The list of operations to perform on the level value
	* `(int) amount`: The value operating by
	* `(enum string) operator`: The operator to use with the `amount` on the level value. Possible values are "+", "-", "\*", "=", "rand".

> [!example] Example: almight_darkness.json
> ```json
> "modifiers": [  
>  {  
>    "type": "kingdomkeys:level",  
>    "operations": [  
>      {  
>        "amount": 2,  
>        "operator": "+"  
>      }  
>    ]  
>  }  
>]
> ```
> Increases the level of spawned mobs by 2
## Spawn
The spawn type `kingdomkeys:spawn` spawns a specified mob in a room when generated.

Here is a breakdown of the JSON structure:
* `(string) entity`: The entity to spawn
* `[optional] (object) additional_data`: The NBT data to spawn the entity with

>[!example] Example: moogle_room.json
>```json
>"modifiers": [
>  {
>    "type": "kingdomkeys:spawn",
>    "additional_data": {
>      "inv": "kingdomkeys:cards",
>      "stationary": true
>    },
>    "entity": "kingdomkeys:moogle"
>  }
>]
>```
>This spawns a moogle with a custom shop inventory and stops the moogle from moving
