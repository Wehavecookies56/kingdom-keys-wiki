---
{"dg-publish":true,"permalink":"/data-driven-customization/gummi-stats-data/"}
---

Gummi block stats are in the `gummi_stats` folder. Each file sets the stats a [[blocks/Gummi blocks\|Gummi block]] adds to a Gummi Ship. The file name is the block id without its colour, eg. `gummi_cube.json` applies to every colour of the Gummi Cube. Every field is optional and the ship's stats are the sum of all its blocks. Here is the JSON file structure:
* `[optional] (integer) weight`: how heavy the block is. A heavier ship needs more `horsepower` to reach its top speed. Default `0`.
* `[optional] (integer) armor`: how much HP the block adds to the ship. Default `0`.
* `[optional] (integer) cost`: how many cost points the block uses in the [[blocks/Gummi Hangar\|Gummi Hangar]]. A ship can't go over the hangar's max cost (set by the `gummiHangarBaseCost`/`gummiHangarLevelCost` [[config/Server config\|Server config]] options and upgraded with chips). Default `1`.
* `[optional] (integer) top_speed`: engines only, the ship's max speed. The ship uses the speeds of its fastest engine. Default `0`.
* `[optional] (integer) low_speed`: engines only, the ship's speed when it doesn't have enough horsepower for its weight. Default `0`.
* `[optional] (integer) horsepower`: engines only, added up for the whole ship. The ship reaches `top_speed` once its total horsepower is at least ⅔ of its total weight, below that its speed goes down towards `low_speed`. Default `0`.
* `[optional] (integer) firepower`: weapons only, the damage of the weapon's shots. Default `0`.
* `[optional] (integer) fuel_per_shot`: weapons only, the fuel used by each shot. Default `0`.
* `[optional] (integer) mobility`: aero blocks only, how much the block improves the ship's handling. Default `0`.

> [!example] Example: dispel_gummi_cone.json
> ```json
> {
>   "armor": 7,
>   "cost": 3,
>   "weight": 1
> }
> ```

> [!example] Example: gummi_thruster.json (engine)
> ```json
> {
>   "armor": 1,
>   "cost": 32,
>   "horsepower": 20,
>   "low_speed": 70,
>   "top_speed": 90,
>   "weight": 1
> }
> ```

> [!example] Example: gummi_fire.json (weapon)
> ```json
> {
>   "armor": 1,
>   "cost": 40,
>   "firepower": 36,
>   "fuel_per_shot": 35,
>   "weight": 1
> }
> ```
