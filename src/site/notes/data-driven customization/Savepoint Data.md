---
{"dg-publish":true,"permalink":"/data-driven-customization/savepoint-data/"}
---

Savepoint data is in the `savepoints` folder. There is one file per savepoint tier: `normal.json`, `linked.json` and `warp.json`. This is also what the [[config/Common config\|Common config]] `savePointMaterials`/`normalSavePointRestoreList`/`fullSavePointRestoreList`/`warpPointRestoreList` options used to control before the system became data-driven. Here is the JSON file structure:
* `(object) materials`: the upgrade material required for each stat's savepoint tier, keys are stat names (`HP`, `MP`, `HUNGER`, `FOCUS`, `DRIVE`, `TIER`), values are the material item id.
* `(string array) restores`: which stats (from the same list above) this savepoint type restores when used.

> [!example] Example: normal.json
> ```json
> {
>   "materials": {
>     "HP": "kingdomkeys:orichalcum",
>     "MP": "kingdomkeys:illusory_crystal",
>     "FOCUS": "kingdomkeys:remembrance_crystal",
>     "HUNGER": "kingdomkeys:hungry_crystal",
>     "DRIVE": "kingdomkeys:evanescent_crystal",
>     "TIER": "kingdomkeys:orichalcumplus"
>   },
>   "restores": [
>     "HP",
>     "MP"
>   ]
> }
> ```
