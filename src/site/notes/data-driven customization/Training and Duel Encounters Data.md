---
{"dg-publish":true,"permalink":"/data-driven-customization/training-and-duel-encounters-data/"}
---

Training encounters are in the `training_encounter` folder and duel encounters in the `duel_encounter` folder. These are the fights started by talking to a Foreteller or an Apprentice (through the `kingdomkeys:start_encounter` action of a [[data-driven customization/Dialogue Data\|Dialogue]], with `"duel": true` for a duel). Subfolders are part of the id, eg. `duel_encounter/spar/apprentice.json` is `kingdomkeys:spar/apprentice`. Both folders use the same format as a [[data-driven customization/Castle Oblivion Data#Room Encounter\|Castle Oblivion Room Encounter]], so the same fields work in all three. Here is the JSON file structure:
* `(object) encounter`: the fight itself, see [[data-driven customization/Castle Oblivion Data#Encounter Types\|Encounter Types]] (currently only `kingdomkeys:wave`).
	* `[optional] (integer) spawn_delay_ticks`: for `kingdomkeys:wave`, the ticks between each enemy of a wave spawning. Default `14`.
* `[optional] (object array) rewards`: items given when the fight is won. Only given the **first** time it's won (when the player doesn't have the `grants` flag yet). Default none.
* `[optional] (integer) experience`: the EXP given every time the fight is won. Default `0`.
* `[optional] (integer) lux`: the Lux given every time the fight is won. Default `0`.
* `[optional] (integer) arena_radius`: the radius of the ring around the NPC where enemies spawn. `0` means the fight happens on the spot, the spawned enemy takes the place of the NPC (used for duels against the Foreteller). Default `7`.
* `[optional] (integer) spawn_points`: how many spawn points are placed around that ring (minimum 1). Default `8`.
* `[optional] (integer) level`: the level of the spawned enemies. `0` means it scales to the player. When started by an Apprentice its own level is used instead. Default `0`.
* `[optional] (string array) requires`: story flags the player needs before they can start the fight. Default none.
* `[optional] (string) grants`: a story flag given when the fight is won. Other encounters can `require` it to make a chain. Default none.
* `[optional] (string) info`: the localization key of the information plaque shown at the top left when the fight starts. Default none.
* `[optional] (string) music`: music to play while the fight is active. Only used in Castle Oblivion rooms.

> [!example] Example: duel_encounter/dynamic.json
> ```json
> {
>   "arena_radius": 0,
>   "encounter": {
>     "type": "kingdomkeys:wave",
>     "interval_ticks": 60,
>     "waves": [
>       {
>         "spawns": [
>           "kingdomkeys:foreteller"
>         ]
>       }
>     ]
>   },
>   "experience": 700,
>   "grants": "kingdomkeys:duel/dynamic",
>   "info": "kingdomkeys.information.duel",
>   "lux": 400,
>   "requires": [
>     "kingdomkeys:duel/hard"
>   ],
>   "rewards": [],
>   "spawn_points": 1
> }
> ```
