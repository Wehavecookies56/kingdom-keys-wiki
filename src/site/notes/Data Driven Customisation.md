---
{"dg-publish":true,"permalink":"/data-driven-customisation/"}
---

Various parts of Kingdom Keys are data driven using JSON files which which allows for customisation via a data pack. See how to create a data pack [here](https://minecraft.wiki/w/Tutorial:Creating_a_data_pack). The namespace folder for Kingdom Keys is simply `kingdomkeys` 
Here is a list of every data driven element:
* Keyblades
* Drive Forms
* Leveling Paths
* Magic
* Moogle Shops
* Synthesis recipes
* Limits
* Organization Weapons
* Castle Oblivion (Not fully functional yet)

## Keyblades
Keyblade data is in the `keyblades` folder, here is the JSON file structure:
* `(string) ability`: the ability given by the Keyblade.
* `(object) base_stats`: 
	* `(integer) mag`: the base magic stat before upgrades.
	* `(integer) str`: the base strength stat before upgrades.
* `(string) description`: the localisation key for the description displayed in the tooltip.
* `(string) keychain`: the keychain item used to summon the Keyblade.
* `(object array) levels`: the order of the elements is important as it is the level order so the 2nd element is for the level 2 upgrade.
	* `(integer) mag`: the magic stat for the level.
	* `(integer) str`: the strength stats for the level.
	* `(object array) recipe`: the material cost to upgrade.
		* `(string) material`: the material item.
		* `(integer) quantity`: the quantity of the material.
* `(float) reach`: the block reach of the Keyblade.

# Drive Forms
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
* `(string array) base_levelup_abilities`: the abilities learnt for the player when levelling up.
* `(string array) driveform_levelup_abilities`: the abilities learnt for the Form when levelling up.
