---
{"dg-publish":true,"permalink":"/data-driven-customization/sell-data/"}
---

Sell price data is in the `sell` folder, and sets the Munny price paid to the player when selling an item to a Moogle. Unlike the other elements only a single file, named exactly `sell.json`, is actually read — so a data pack override must also be named `sell.json` to take effect. The JSON is a flat array where each entry has:
* `(string) item`: the item id.
* `(integer) price`: the Munny price paid for it.

> [!example] Example: sell.json (first entries)
> ```json
> [
>   {
>     "item": "kingdomkeys:winner_stick",
>     "price": 500
>   },
>   {
>     "item": "minecraft:coal",
>     "price": 10
>   }
> ]
> ```
