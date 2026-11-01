---
{"dg-publish":true,"permalink":"/data-driven-customization/gummi-ships-data/"}
---

Gummi Ship data is in the `gummi_ships` folder. Each file is a premade Gummi Ship that is turned into a Gummi Ship Blueprint item (shown in the creative Gummi tab and usable in the [[blocks/Gummi Hangar\|Gummi Hangar]]). The file id is the ship id, eg. `gummi_ships/highwind.nbt` is `kingdomkeys:highwind`.

These are **NBT files, not JSON**, and aren't written by hand. Build the ship in a [[blocks/Gummi Hangar\|Gummi Hangar]] and save it: saved ships are written to `<game folder>/kingdomkeys/gummi_ships/<name>.nbt`. Copy that file to `data/<namespace>/gummi_ships/` in your data pack. Files bigger than 8 MB (uncompressed) are rejected.

# Gummi Blueprint loot modifier
To make a ship blueprint appear in chest loot, add a NeoForge global loot modifier (in `loot_modifiers`, and listed in `data/neoforge/loot_modifiers/global_loot_modifiers.json`) of type `kingdomkeys:gummi_blueprint`:
* `(string) type`: must be `"kingdomkeys:gummi_blueprint"`.
* `(object array) conditions`: vanilla/NeoForge loot conditions deciding which loot tables and how often, eg. `neoforge:loot_table_id` and `minecraft:random_chance`.
* `(string) ship`: the id of the ship in the `gummi_ships` folder. If no data pack provides it, nothing is added and a warning is logged.

> [!example] Example: loot_modifiers/highwind_end_city.json
> ```json
> {
>   "type": "kingdomkeys:gummi_blueprint",
>   "conditions": [
>     {
>       "condition": "neoforge:loot_table_id",
>       "loot_table_id": "minecraft:chests/end_city_treasure"
>     },
>     {
>       "chance": 0.25,
>       "condition": "minecraft:random_chance"
>     }
>   ],
>   "ship": "kingdomkeys:highwind"
> }
> ```
