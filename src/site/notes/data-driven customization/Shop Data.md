---
{"dg-publish":true,"permalink":"/data-driven-customization/shop-data/"}
---

# Shop
Moogle synthesis shop listings are in the `shop` folder, this defines what a Moogle offers to synthesise/sell to the player (as opposed to what it will buy from the player, see [[data-driven customization/Sell Data\|Sell]]), along with the price and requirements. Each file is a flat array; the first entry of a file can optionally be a `names` directive linking the shop to a name list (see [[#Shop Names]]) instead of an item entry.
* `[optional] (string) names`: only valid as the very first entry in the array, links this shop list to a name list registered in the `shop/names` folder, used for the Moogle's random display name. Only the first entry with this key is read, any further ones are ignored.
* Item entries:
	* `(string) item`: the item id sold.
	* `(integer) amount`: how many are given per purchase.
	* `(integer) tier`: the item's tier, gated by the `requireSynthTierShop` server config option.
	* `(integer) cost`: the Munny cost.
	* `[optional] (integer) mat_req`: the minimum amount of a held material required to unlock buying this item. If not set defaults to 0 (no requirement).
	* `[optional] (string) condition`: set to `"all"` to require holding all of the `mat_req` materials rather than just one. If not set defaults to requiring any.

> [!example] Example: default.json (first entries)
> ```json
> [
>   { "names": "kingdomkeys:default" },
>   {
>     "amount": 1,
>     "condition": "all",
>     "cost": 80,
>     "item": "kingdomkeys:blazing_shard",
>     "mat_req": 30,
>     "tier": 1
>   }
> ]
> ```

# Shop Names
Moogle name pools are in the `shop/names` folder, a separate registry from the shop listings above. Each file is a flat array of name strings used as the random display name pool for a Moogle using the linked shop.

> [!example] Example: default.json (first entries)
> ```json
> [
>   "Artemicion",
>   "Elmina",
>   "Good King Moggle Mog XII",
>   "Gumo"
> ]
> ```
