---
{"dg-publish":true,"permalink":"/data-driven-customization/drive-forms-data/"}
---

Drive Form data is in the `driveforms` folder, here is the JSON file structure:
* `(integer) cost`: the Drive Point cost to use the Form.
* `(integer) ap`: the [[Anti Form\|Anti Point]] increase (can be negative).
* `(bool) can_go_anti`: whether using the Form can trigger [[Anti Form\|Anti Form]].
* `(bool) can_use_magic`: whether magic is usable in the Form.
* `(float) str_mult`: the strength multiplier when using the Form.
* `(float) mag_mult`: the magic multiplier when using the Form.
* `(float) speed_mult`: the movement speed multiplier when using the Form.
* `(integer array) level_up`: the exp needed for the Form levels.
* `(string array) abilities`: the abilities the Form has.
* `(string array) base_levelup_abilities`: the abilities learnt for base form when levelling up.
* `(string array) driveform_levelup_abilities`: the abilities learnt for the Form when levelling up.

> [!example] Example: form_valor.json
> ```json
> {
>   "abilities": [
>     "kingdomkeys:ability_synch_blade"
>   ],
>   "ap": 1,
>   "base_levelup_abilities": [
>     "",
>     "kingdomkeys:ability_auto_valor",
>     "kingdomkeys:ability_high_jump",
>     "kingdomkeys:ability_superjump",
>     "kingdomkeys:ability_high_jump",
>     "kingdomkeys:ability_superjump",
>     "kingdomkeys:ability_high_jump"
>   ],
>   "can_go_anti": true,
>   "can_use_magic": false,
>   "cost": 300,
>   "driveform_levelup_abilities": [
>     "kingdomkeys:ability_high_jump",
>     "",
>     "kingdomkeys:ability_high_jump",
>     "",
>     "kingdomkeys:ability_high_jump",
>     "",
>     "kingdomkeys:ability_high_jump"
>   ],
>   "level_up": [
>     0,
>     80,
>     240,
>     520,
>     968,
>     1528,
>     2200
>   ],
>   "mag_mult": 1.0,
>   "speed_mult": 1.4,
>   "str_mult": 1.2
> }
> ```
> A `""` empty string entry in `base_levelup_abilities`/`driveform_levelup_abilities` just means no ability is learnt at that particular Form level.
