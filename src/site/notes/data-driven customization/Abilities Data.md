---
{"dg-publish":true,"permalink":"/data-driven-customization/abilities-data/"}
---

Ability data is in the `abilities` folder. These files can only **change** abilities that already exist in the mod (the file name must match the ability id, eg. `ability_aerial_dodge.json` for `kingdomkeys:ability_aerial_dodge`), they can't create new ones. A file for an ability that doesn't exist is ignored with a warning. Every field is optional, anything left out keeps the ability's built in value. Here is the JSON file structure:
* `[optional] (integer) ap_cost`: the AP needed to equip the ability.
* `[optional] (integer) order`: the position of the ability in the abilities menu, lower numbers are shown first.
* `[optional] (string) exclusion_group`: abilities sharing the same group can't be equipped at the same time, the others grey out while one is equipped. `null` keeps the built in group.
* `[optional] (enum string) type`: the kind of ability. Possible values "ACTION", "GROWTH", "GROWTH_STACKABLE", "SUPPORT", "WEAPON", "ACCESSORY". An unknown value is ignored with a warning.

> [!example] Example: ability_aerial_dodge.json
> ```json
> {
>   "type": "GROWTH",
>   "ap_cost": 3,
>   "order": 11
> }
> ```
