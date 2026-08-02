---
{"dg-publish":true,"permalink":"/data-driven-customization/magic-data/"}
---

Magic data is in the `magics` folder, here is the JSON file structure:
* `(integer) cost`: the MP cost to cast the spell.
* `(integer) casttime`: how many ticks the cast animation takes.
* `(integer) cooldown`: the cooldown in ticks before the spell(s) can be cast again. When the `perMagicCooldown` server config is enabled this value is multiplied by `perMagicCooldownMultiplier` and each spell gets its own independent cooldown, otherwise a single shared cooldown applies to every spell.
* `(float) dmg_mult`: the damage multiplier at level 1.
* `[optional] (float) dmg_mult_max`: the damage multiplier at max level. If not set (or 0) `dmg_mult` is used for every level.
* `(bool) magic_lock_on`: whether the spell can lock onto a target by using magic lock on.
* `(integer) max_exp`: the exp needed to max out the spell.
* `(integer) max_lvl`: the max level for the spell.
* `[optional] (string) next_tier`: the id of the next tier spell (eg. Fire → Fira). If not set the spell has no next tier.
* `[optional] (string) magic_rc`: the id of the Reaction Command tied to casting the spell. If not set there is none.
* `(enum string) spell_type`: whether the spell counts as physical or magic damage. Possible values "PHYSICAL", "MAGIC"

> [!example] Example: magic_thundara.json
> ```json
> {
>   "casttime": 10,
>   "cooldown": 35,
>   "cost": 14,
>   "dmg_mult": 0.11,
>   "dmg_mult_max": 0.114,
>   "magic_lock_on": true,
>   "magic_rc": "kingdomkeys:magic_thunder",
>   "max_exp": 2400,
>   "max_lvl": 3,
>   "next_tier": "kingdomkeys:magic_thundaga",
>   "spell_type": "MAGIC"
> }
