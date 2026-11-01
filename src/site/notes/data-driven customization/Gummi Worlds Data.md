---
{"dg-publish":true,"permalink":"/data-driven-customization/gummi-worlds-data/"}
---

Gummi World data is in the `gummi_worlds` folder. Each file adds one world to the Gummi Ship Ocean Between (the `ocean_between` dimension): where its marker sits, where you appear when landing on it and leaving it, and a few rules for the world's dimension. The world itself must be an existing dimension, either vanilla (eg. `minecraft:overworld`) or one added by a data pack, see [[data-driven customization/Prebuilt Worlds Data\|Prebuilt Worlds]] for how the Kingdom Keys worlds are built. Here is the JSON file structure:
* `(string) dimension`: the id of the dimension this world takes you to. **Required**.
* `[optional] (double) takeoff_altitude`: the Y level a piloted Gummi Ship has to reach inside the world before the Launch reaction command appears to fly off to the Ocean Between. Default `320`.
* `(array of 3 numbers) worldmap_position`: the `[x, y, z]` position of the world's marker on the Ocean Between. **Required**.
* `[optional] (array of 3 numbers) takeoffSpawn`: the `[x, y, z]` position on the Ocean Between where the ship appears after leaving this world. Default is `worldmap_position` moved `scale` blocks along Z.
* `(array of 3 numbers) landingSpawn`: the `[x, y, z]` position inside the world's dimension where the player appears after landing. **Required**.
* `[optional] (array of 2 numbers) takeoffRotation`: the `[yaw, pitch]` the player faces after leaving this world. If not set the player keeps facing the same way.
* `[optional] (array of 2 numbers) landingRotation`: the `[yaw, pitch]` the player faces after landing on this world. If not set the player keeps facing the same way.
* `[optional] (string) texture`: the texture drawn for the world on the Ocean Between. Default `kingdomkeys:textures/worldmap/<dimension name>.png`.
* `[optional] (float) scale`: the size of the world on the Ocean Between, in blocks. Default `24`.
* `[optional] (double) approach_range`: how close (in blocks) the ship has to get to the marker for the Land reaction command to appear. Default is the same as `scale`.
* `[optional] (bool) build`: whether players can place and break blocks in this world. Right click interactions (doors, chests, buttons...) always work, and operators can always build. Default `true`.
* `[optional] (bool) vanilla_mobs`: whether non Kingdom Keys mobs can naturally spawn in this world. Default `true`.
* `[optional] (bool) mob_griefing`: whether mobs can break or change blocks in this world. Default `true`.
* `[optional] (bool) unlocked_by_default`: whether the world is shown on the Ocean Between from the start. If `false` it shows up as an unknown world until the player reaches it for the first time. Default `false`.
* `[optional] (string or integer) marker_colour`: the colour of the world's marker and arrow on the HUD, as a hex string (eg. `"#4FE3E3"`, alpha is ignored) or an integer. Default `#FFFFFF`.

> [!example] Example: daybreak_town.json
> ```json
> {
>   "dimension": "kingdomkeys:daybreak_town",
>   "takeoff_altitude": 320,
>   "worldmap_position": [-250, 128, 800],
>   "takeoffRotation": [180, 0],
>   "landingRotation": [0, 0],
>   "takeoffSpawn": [-250, 128, 780],
>   "landingSpawn": [106, 100, 26],
>   "texture": "kingdomkeys:textures/worldmap/daybreak_town.png",
>   "scale": 32,
>   "approach_range": 40,
>   "build": true,
>   "mob_griefing": false,
>   "vanilla_mobs": false,
>   "unlocked_by_default": true,
>   "marker_colour": "#A45FD6"
> }
> ```
