---
{"dg-publish":true,"permalink":"/data-driven-customization/shotlocks-data/"}
---

Shotlock data is in the `shotlocks` folder, here is the JSON file structure:
* `(integer) cooldown`: ticks between each lock at level 1.
* `[optional] (integer) cooldown_max`: ticks between each lock at max level, interpolated between `cooldown` and this as the Shotlock levels up. If not set (or 0) `cooldown` is used for every level.
* `(integer) max`: the max number of locks.
* `(float) dmg_mult`: the damage multiplier at level 1.
* `[optional] (float) dmg_mult_max`: the damage multiplier at max level, interpolated the same way as `cooldown_max`. If not set (or 0) `dmg_mult` is used for every level.
* `(integer) max_exp`: the exp needed to max out the Shotlock.
* `[optional] (integer) max_level`: the max level for the Shotlock. If not set (or 0) defaults to 1.
* `[optional] (string) element`: the elemental type of the Shotlock. If not set defaults to none.
* `[optional] (string) minigame`: which follow-up minigame a fully charged Shotlock (level 2+) triggers, possible values `mash`, `mash_dash`, `timing`, `keys`, or leave unset/empty for none. This only triggers when the `shotlockMinigames` server config is enabled.

> [!example] Example: absolute_zero.json
> ```json
> {
>   "cooldown": 5,
>   "cooldown_max": 3,
>   "dmg_mult": 1.3,
>   "dmg_mult_max": 1.56,
>   "element": "ice",
>   "max": 12,
>   "max_exp": 6400,
>   "max_level": 4,
>   "minigame": "keys"
> }
> ```
