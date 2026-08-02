---
{"dg-publish":true,"permalink":"/data-driven-customization/synthesis-recipes-data/"}
---

>[!warn] Don't confuse this with the `recipe` folder
> `data/kingdomkeys/recipe/` is vanilla Minecraft's crafting recipe registry (ordinary crafting table recipes) and is unrelated to this system. Moogle Shop synthesis recipes (this) actually live in the `synthesis` folder instead. Keyblade forge upgrade recipes are a separate system too, see [[data-driven customization/Keyblades Data\|Keyblades]].

Synthesis recipe data (for armor, accessories and items bought/synthesised at a Moogle) is in the `synthesis` folder, here is the JSON file structure:
* `(object array) ingredients`: the materials required.
	* `(string) material`: the material item id.
	* `(integer) quantity`: how much of it is required.
* `(integer) cost`: the Munny cost to synthesise.
* `[optional] (integer) exp`: the exp given. If not set no exp is given.
* `(object) output`:
	* `(string) item`: the id of the result item.
	* `(integer) quantity`: how many are given.
	* `(string) type`: the type of item (eg. `item`, `keyblade`).
* `(integer) tier`: the synthesis tier, gated by the `requireSynthTier` (for synthesising it) and `requireSynthTierShop` (for buying an already-synthesised one) server config options.

> [!example] Example: abaddon_plasma.json
> ```json
> {
>   "cost": 0,
>   "ingredients": [
>     { "material": "kingdomkeys:soothing_gem", "quantity": "2" },
>     { "material": "kingdomkeys:soothing_crystal", "quantity": "3" },
>     { "material": "kingdomkeys:writhing_stone", "quantity": "4" }
>   ],
>   "output": {
>     "type": "keyblade",
>     "item": "kingdomkeys:abaddon_plasma_chain",
>     "quantity": 1
>   },
>   "tier": 4
> }
> ```
