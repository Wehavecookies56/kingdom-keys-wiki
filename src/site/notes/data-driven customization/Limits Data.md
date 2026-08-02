---
{"dg-publish":true,"permalink":"/data-driven-customization/limits-data/"}
---

Limit data is in the `limits` folder, here is the JSON file structure:
* `(integer) cost`: the Drive gauge cost to use the Limit.
* `(integer) cooldown`: the cooldown in ticks before the Limit can be used again.
* `(float) dmg_mult`: the damage multiplier for the Limit.

> [!example] Example: arrow_rain.json
> ```json
> {
>   "cooldown": 600,
>   "cost": 300,
>   "dmg_mult": 1.0
> }
> ```
