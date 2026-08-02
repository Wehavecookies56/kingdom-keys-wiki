---
{"dg-publish":true,"permalink":"/data-driven-customization/organization-weapons-data/"}
---

Organization Weapon data is in the `organization` folder. Unlike most of the other elements in [[data-driven customization/Data Driven Customisation\|Data Driven Customisation]], these files are hand written directly rather than build-generated, and they attach extra data to an existing Organization weapon item rather than creating a new one. Here is the JSON file structure:
* `(object) base_stats`:
	* `(integer) str`: the base strength stat.
	* `(integer) mag`: the base magic stat.
* `(string) description`: the description shown in the tooltip, can be empty.
* `[optional] (float) reach`: the block reach of the weapon. If not set defaults to 0.
* `[optional] (string array) abilities`: abilities the weapon grants. If not set the weapon has none.

> [!example] Example: abandoned_dogma.json
> ```json
> {
> 	"base_stats": {
> 		"str": 12,
> 		"mag": 17
> 	},
> 	"description": "Test description"
> }
> ```
