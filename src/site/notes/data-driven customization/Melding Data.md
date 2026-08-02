---
{"dg-publish":true,"permalink":"/data-driven-customization/melding-data/"}
---

Melding data is in the `melding` folder, here is the JSON file structure:
* `(string) ingredient1`: the id of the first magic item required.
* `(string) ingredient2`: the id of the second magic item required.
* `(integer) cost`: the Munny cost to meld.
* `(object) output`: the main result.
	* `(string) item`: the id of the result item.
	* `(integer) quantity`: how many are given.
	* `(string) type`: the type of item, used to know how to display/handle the result (eg. `item`).
* `[optional] (object) output2`: a secondary/bonus result. If not set there is no bonus.
	* `(string) item`: the id of the bonus result item.
	* `(integer) quantity`: how many are given.
	* `[optional] (integer) chance`: percent chance of getting the bonus result. If not set defaults to 0 (never).
* `(integer) tier`: the melding tier. When the `requireMeldingTier` server config is enabled players can only meld recipes from their tier or lower.

> [!example] Example: fission_firaga.json
> ```json
> {
>   "cost": 1000,
>   "ingredient1": "kingdomkeys:spellfira",
>   "ingredient2": "kingdomkeys:spellaeroga",
>   "output": {
>      "type": "item",
>      "item": "kingdomkeys:spellfissionfiraga",
>      "quantity": 1
>   },
>   "output2": {
>       "chance": 20,
>       "item": "kingdomkeys:spellfiragaburst",
>       "quantity": 1
>   },
>   "tier": 4
> }