---
{"dg-publish":true,"permalink":"/data-driven-customization/dialogue-data/"}
---

Dialogue data is in the `dialogue` folder. Each file is a conversation tree used by the NPCs that talk to the player: the Apprentices use `apprentice`, and the Foretellers use `foreteller` (or `foreteller_first_meeting` the first time you meet them). A Foreteller's dialogue can also be changed with the `dialogue` NBT tag on the entity. A dialogue is made of nodes: each node shows some lines and then a list of answers the player can pick, and each answer can jump to another node and/or run actions. Here is the JSON file structure:
* `[optional] (string) start`: the name of the node the conversation starts at. Default `"start"`.
* `(object) nodes`: every node of the conversation, keyed by its name.
	* `(string array) lines`: the localisation keys of the lines the NPC says.
	* `[optional] (bool) pick`: if `true` only one of the `lines` is said, chosen at random, instead of all of them in order. Default `false`.
	* `[optional] (object array) answers`: the answers the player can choose. If empty the conversation ends after the lines.
		* `(string) text`: the localisation key of the answer's text.
		* `[optional] (string) goto`: the name of the node to go to when picked. If not set the conversation ends.
		* `[optional] (object array) if`: conditions that must **all** be true for the answer to be shown, see [[#Conditions]].
		* `[optional] (object array) do`: actions run when the answer is picked, see [[#Actions]].

> [!example] Example: apprentice.json (greeting lines cut for brevity)
> ```json
> {
>   "nodes": {
>     "start": {
>       "answers": [
>         {
>           "do": [
>             {
>               "type": "kingdomkeys:start_encounter",
>               "duel": true,
>               "encounter": "kingdomkeys:spar/apprentice"
>             }
>           ],
>           "text": "kingdomkeys.dialogue.apprentice.answer.spar"
>         },
>         {
>           "do": [
>             {
>               "type": "kingdomkeys:close"
>             }
>           ],
>           "text": "kingdomkeys.dialogue.apprentice.answer.leave"
>         }
>       ],
>       "lines": [
>         "kingdomkeys.dialogue.apprentice.greeting.1",
>         "kingdomkeys.dialogue.apprentice.greeting.2",
>         "kingdomkeys.dialogue.apprentice.greeting.3"
>       ],
>       "pick": true
>     }
>   }
> }
> ```

# Conditions
Every condition has a `(string) type` plus its own options:
* `kingdomkeys:flag`: checks a story flag on the player.
	* `(string) flag`: the flag id.
	* `[optional] (bool) present`: `true` passes if the player has the flag, `false` if they don't. Default `true`.
* `kingdomkeys:can_start`: passes if the player meets the `requires` flags of a [[data-driven customization/Training and Duel Encounters Data\|training or duel encounter]].
	* `[optional] (bool) duel`: `true` looks in `duel_encounter`, `false` in `training_encounter`. Default `false`.
	* `(string) encounter`: the encounter id.
* `kingdomkeys:level`: checks the player's level.
	* `[optional] (integer) min`: the minimum level. Default `0`.
	* `[optional] (integer) max`: the maximum level. Default no limit.
* `kingdomkeys:union`: passes if the player is in a Union.
	* `[optional] (enum string) union`: the Union to check for. Possible values "none", "unicornis", "leopardos", "vulpes", "anguis", "ursus". If not set, it's the Union of the Foreteller speaking.

# Actions
Every action has a `(string) type` plus its own options. Actions marked as *ends* close the conversation after running.
* `kingdomkeys:start_encounter` (*ends*): starts a [[data-driven customization/Training and Duel Encounters Data\|training or duel encounter]].
	* `[optional] (bool) duel`: `true` looks in `duel_encounter`, `false` in `training_encounter`. Default `false`.
	* `(string) encounter`: the encounter id.
* `kingdomkeys:give_item`: gives an item to the player (dropped if the inventory is full).
	* `(object) item`: the item stack, eg. `{ "id": "minecraft:apple", "count": 1 }`.
* `kingdomkeys:set_flag`: adds or removes a story flag on the player.
	* `(string) flag`: the flag id.
	* `[optional] (bool) set`: `true` adds it, `false` removes it. Default `true`.
* `kingdomkeys:open_portal` (*ends*): opens a portal next to the NPC.
	* `(string) dimension`: the dimension the portal leads to.
	* `[optional] (array of 3 integers) pos`: the `[x, y, z]` position the portal leads to. If not set and the speaker is a Foreteller, it leads to their post in Daybreak Town.
	* `[optional] (string) until`: a flag; the portal stays open until the player has it.
* `kingdomkeys:return_home` (*ends*): opens a portal back to where the player came from before the last `open_portal`.
	* `[optional] (string) grants`: a flag given to the player when they go through it.
* `kingdomkeys:open_shop` (*ends*): opens the speaking Foreteller's shop.
* `kingdomkeys:close` (*ends*): just ends the conversation.
