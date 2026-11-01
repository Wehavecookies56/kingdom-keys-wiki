---
{"dg-publish":true,"permalink":"/data-driven-customization/prebuilt-worlds-data/"}
---

Prebuilt worlds are the hand built Kingdom Keys worlds (eg. Destiny Islands, Daybreak Town). They have two parts:
* The world's blocks, in the `kk_worlds/<world name>/` folder. These are **NBT files, not JSON**, and aren't written by hand: they're produced in game with the `/kingdomkeys export` command (see [[#Exporting a world]]).
* A dimension JSON in the `dimension` folder that uses the `kingdomkeys:prebuilt_world_generator` generator to rebuild those blocks chunk by chunk.

The `dimension` and `dimension_type` files are vanilla Minecraft data pack files (see [dimension](https://minecraft.wiki/w/Dimension_definition) and [dimension type](https://minecraft.wiki/w/Dimension_type) on the Minecraft wiki), only the generator is specific to Kingdom Keys. To make a new world reachable with the Gummi Ship it also needs a [[data-driven customization/Gummi Worlds Data\|Gummi World]] file.

# Prebuilt world generator
Set as the `generator` of a dimension JSON, here is its structure:
* `(string) type`: must be `"kingdomkeys:prebuilt_world_generator"`.
* `(string) world`: the id of the `kk_worlds` folder to build from, eg. `kingdomkeys:destiny_islands` reads `data/kingdomkeys/kk_worlds/destiny_islands/`.
* `[optional] (array of 3 integers) origin`: the `[x, y, z]` position where the lowest corner of the export is placed. X and Z should be multiples of 16 so the pieces line up with chunks. Default `[0, 0, 0]`.
* `(object) biome_source`: a vanilla biome source, eg. `{ "type": "minecraft:fixed", "biome": "minecraft:warm_ocean" }`. Biome features (ores, plants...) are **not** generated, only the exported blocks.
* `[optional] (object) sea`: a sea poured around the build so the world sits in an ocean. If not set, everything outside the build is void.
	* `[optional] (string) water`: the block the sea is made of. Default `minecraft:water`.
	* `(integer) level`: the Y of the water surface (exclusive, like vanilla's sea level).
	* `(integer) floor`: the average Y of the top of the sea bed. Match it to the sea bed of the export so there is no visible seam.
	* `[optional] (integer) variation`: how many blocks below `floor` the sea bed is allowed to dip. Default `3`.
	* `[optional] (integer) surface_depth`: how many blocks of `surface` are placed on top of `body`. Default `4`.
	* `[optional] (string) body`: the block for the bulk of the sea bed. Default `minecraft:stone`.
	* `[optional] (string) surface`: the block covering the sea bed. Default `minecraft:sand`.
	* `[optional] (string) patches`: a block scattered through the surface for variety, eg. gravel or clay. If not set there are no patches.
	* `[optional] (string) bedrock`: the block placed at the very bottom of the world. If not set the bottom is left open.

> [!example] Example: dimension/daybreak_town.json
> ```json
> {
>   "type": "kingdomkeys:daybreak_town",
>   "generator": {
>     "type": "kingdomkeys:prebuilt_world_generator",
>     "world": "kingdomkeys:daybreak_town",
>     "origin": [0, 64, 0],
>     "sea": {
>       "water": "minecraft:water",
>       "level": 66,
>       "floor": 64,
>       "variation": 2,
>       "surface_depth": 4,
>       "body": "minecraft:stone",
>       "surface": "minecraft:sand",
>       "bedrock": "minecraft:bedrock"
>     },
>     "biome_source": { "type": "minecraft:fixed", "biome": "minecraft:warm_ocean" }
>   }
> }
> ```

# Exporting a world
Build the world in any dimension (creative works best), then run as an operator:

`/kingdomkeys export <name> <from> <to> [entities]`

* `name`: the folder name the export is saved as.
* `from` / `to`: two opposite corners of the area to export. The area is extended to whole chunks horizontally.
* `[optional] entities`: whether to also save entities like paintings, item frames and armor stands. Default `true`.

The files are written to `<game folder>/kingdomkeys/exports/<name>/`: a `manifest.nbt` plus one `<x>_<z>.nbt` piece per chunk (empty chunks get no file). Running the command again with the same name **merges** into the existing export, so a big world can be exported in several parts. Copy the whole folder to `data/<namespace>/kk_worlds/<name>/` in your data pack and point a dimension's `world` field at it.
