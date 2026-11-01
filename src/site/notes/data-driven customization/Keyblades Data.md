---
{"dg-publish":true,"permalink":"/data-driven-customization/keyblades-data/"}
---

Keyblade data is in the `keyblades` folder, here is the JSON file structure:
* `(string) ability`: the ability given by the Keyblade.
* `(object) base_stats`: 
	* `(integer) mag`: the base magic stat before upgrades.
	* `(integer) str`: the base strength stat before upgrades.
* `(string) description`: the localisation key for the description displayed in the tooltip.
* `[optional] (array of strings or single string) hit_particles`: the particle(s) spawned when the Keyblade hits something. Can be a single particle id or an array of several.
* `[optional] (float) hit_particle_scale`: the scale of the hit particles. Default `0.35`.
* `(string) keychain`: the keychain item used to summon the Keyblade.
* `(object array) levels`: the order of the elements is important as it is the level order so the 2nd element is for the level 2 upgrade.
	* `(integer) mag`: the magic stat for the level.
	* `(integer) str`: the strength stats for the level.
	* `(object array) recipe`: the material cost to upgrade.
		* `(string) material`: the material item.
		* `(integer) quantity`: the quantity of the material.
* `(float) reach`: the block reach of the Keyblade.
* `[optional] (string) sound`: the sound event played when the Keyblade hits something. Must be a registered sound event id. Default `kingdomkeys:keyblade_hit/generic_hit`.

> [!example] Example: oblivion.json (first 2 of 10 levels, rest cut for brevity)
> ```json
> {
>   "ability": "kingdomkeys:ability_drive_boost",
>   "base_stats": {
>     "mag": 5,
>     "str": 8
>   },
>   "description": "item.kingdomkeys.oblivion.desc",
>   "hit_particles": ["kingdomkeys:textures/particle/oblivion_hit.png"],
>   "keychain": "kingdomkeys:oblivion_chain",
>   "levels": [
>     {
>       "mag": 6,
>       "str": 8,
>       "recipe": [
>         { "material": "kingdomkeys:fluorite", "quantity": 1 },
>         { "material": "kingdomkeys:writhing_crystal", "quantity": 2 }
>       ]
>     },
>     {
>       "mag": 6,
>       "str": 9,
>       "recipe": [
>         { "material": "kingdomkeys:fluorite", "quantity": 1 },
>         { "material": "kingdomkeys:writhing_crystal", "quantity": 3 }
>       ]
>     }
>   ],
>   "reach": 1.0,
>   "sound": "kingdomkeys:keyblade_hit/oblivion_hit"
> }
> ```
