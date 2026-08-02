---
{"dg-publish":true,"permalink":"/data-driven-customization/keyblades-data/"}
---

Keyblade data is in the `keyblades` folder, here is the JSON file structure:
* `(string) ability`: the ability given by the Keyblade.
* `(object) base_stats`: 
	* `(integer) mag`: the base magic stat before upgrades.
	* `(integer) str`: the base strength stat before upgrades.
* `(string) description`: the localisation key for the description displayed in the tooltip.
* `(string) keychain`: the keychain item used to summon the Keyblade.
* `(object array) levels`: the order of the elements is important as it is the level order so the 2nd element is for the level 2 upgrade.
	* `(integer) mag`: the magic stat for the level.
	* `(integer) str`: the strength stats for the level.
	* `(object array) recipe`: the material cost to upgrade.
		* `(string) material`: the material item.
		* `(integer) quantity`: the quantity of the material.
* `(float) reach`: the block reach of the Keyblade.

> [!example] Example: abyssal_tide.json (first 2 of 10 levels, rest cut for brevity)
> ```json
> {
>   "ability": "kingdomkeys:ability_water_boost",
>   "base_stats": {
>     "mag": 2,
>     "str": 5
>   },
>   "description": "item.kingdomkeys.abyssal_tide.desc",
>   "keychain": "kingdomkeys:abyssal_tide_chain",
>   "levels": [
>     {
>       "mag": 3,
>       "str": 5,
>       "recipe": [
>         { "material": "kingdomkeys:fluorite", "quantity": 1 },
>         { "material": "kingdomkeys:pulsing_stone", "quantity": 3 }
>       ]
>     },
>     {
>       "mag": 3,
>       "str": 6,
>       "recipe": [
>         { "material": "kingdomkeys:fluorite", "quantity": 1 },
>         { "material": "kingdomkeys:pulsing_stone", "quantity": 4 }
>       ]
>     }
>   ],
>   "reach": 1.0
> }
> ```
