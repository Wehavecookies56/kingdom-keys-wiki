---
{"dg-publish":true,"permalink":"/data-driven-customization/leveling-data/"}
---

Leveling data is in the `leveling` folder, there is one file per path (`warrior.json`, `mystic.json`, `guardian.json`) defining the stat and reward growth for every level from 0 to 100. These files are long so only a 3-level excerpt is shown below instead of a full example:
* `[optional] (integer) version`: a version number for the file, only used to log a warning if it looks out of date. If missing it defaults to 0 and a warning is logged.
* `[optional] (object) levels`: a map where each key is a level number written as a string (`"0"` to `"100"`) and the value is an object describing what that level grants. For backwards compatibility, if this key is missing entirely the whole root object is read as if it were the levels map itself.
	* Each level entry can contain any of the following, all optional — anything left out simply grants nothing extra for that level:
		* `(integer) ap`: AP gained.
		* `(integer) str`: Strength gained.
		* `(integer) mag`: Magic gained.
		* `(integer) def`: Defense gained.
		* `(integer) maxhp`: Max HP gained.
		* `(integer) maxmp`: Max MP gained.
		* `(string array) abilities`: abilities unlocked at this level.
		* `(object array) items`: reward items granted at this level, each is a regular item stack (eg. `{"id": "kingdomkeys:potion", "count": 1}`).
		* `(integer) max_accessories`: increase to the accessory slot count.
		* `(integer) max_armors`: increase to the armor slot count.
		* `(integer) max_magics`: increase to the magic slot count.

>[!warn] Level 0 is special — it's a Station of Awakening "sacrifice" penalty, not a normal level
> At the [[Systems/Station of Awakening\|Station of Awakening]] a player picks one path to keep (their **choice**) and gives up one of the other two (their **sacrifice**). The path that's kept applies its level 1 data as normal, but the path picked as the sacrifice has its **level 0** entry applied once as a stat penalty — this is the only time level 0 is ever read, it's unreachable through normal levelling. The third path (neither chosen nor sacrificed) contributes nothing at all. This is why every path's level 0 only ever contains a single negative stat: Warrior removes 1 Strength, Mystic removes 1 Magic, and Guardian removes 1 Defense.

>[!warn] Level 1 is used as a way to give the player default abilities too.
>Level 1 only ever contains a single positive stat: Warrior adds 1 Strength, Mystic adds 1 Magic, and Guardian adds 1 Defense.
>It also grants the ability Zero Exp regardless of the choice as it's present in all 3 paths.

> [!example] Example: guardian.json (levels 0-2, out of 101 total)
> ```json
> {
>   "version": 3,
>   "levels": {
>     "0": { "def": -1 },
>     "1": {
>       "def": 1,
>       "ap": 10,
>       "abilities": ["kingdomkeys:ability_zero_exp"]
>     },
>     "2": {
>       "def": 1,
>       "abilities": ["kingdomkeys:ability_scan"]
>     }
>   }
> }
> ```
