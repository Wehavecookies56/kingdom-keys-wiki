---
{"dg-publish":true,"permalink":"/config/client-config/"}
---


Here you'll find all client options which don't affect gameplay, server cannot enfoce those.

General:

|Name|Description|Default|Type|
|---|---|---|---|
|summonTogether|Summon both Keyblade and Armor with Summon Keyblade key.|false|boolean|
|auto3rdPersonShip|Automatically change to 3rd person when riding a gummi ship.|true|boolean|

GUI:

|Name|Description|Default|Type|
|---|---|---|---|
|showGuiToggle|Toggle HUD visibility. Weapon option only shows while holding a Keyblade or Organization weapon.|SHOW|enum|
|showDriveForms|Drive Forms Visibility.|true|boolean|

Command Menu:

|Name|Description|Default|Type|
|---|---|---|---|
|cmChangeColor|Allow the Command Menu to change colors based on nearby enemies.|true|boolean|
|magicDisplayedInCommandMenu|Magic displayed in the Magic submenu.|list of magic IDs|list|
|cmTextXOffset|Command Menu Text X Offset.|0|integer (-1000-1000)|
|cmHeaderTextVisibility|Command Menu Header Text Visibility.|true|boolean|
|cmClassicColors|Command Menu classic color scheme.|false|boolean|
|cmXScale|Command Menu X Scale %.|100|integer (-1000-1000)|
|cmXPos|Command Menu X Position.|0|integer (-1000-1000)|
|cmSelectedXOffset|Command Menu Selected X Offset.|5|integer (-1000-1000)|
|cmSubXOffset|Command Menu Submenu X Offset %.|100|integer (-1000-1000)|
|cmEndLWidth|Command Menu Element Left End Segment Width.|10|integer (0-256)|
|cmEndRWidth|Command Menu Element Right End Segment Width.|10|integer (0-256)|
|cmHeaderEndLWidth|Command Menu Header Left End Segment Width.|10|integer (0-256)|
|cmHeaderEndRWidth|Command Menu Header Right End Segment Width.|15|integer (0-256)|
|cmReactionEndLWidth|Reaction command left end segment width.|10|integer (0-256)|
|cmReactionEndRWidth|Reaction command right end segment width.|10|integer (0-256)|

HP Bar:

|Name|Description|Default|Type|
|---|---|---|---|
|hpXPos|Health Bar X Position.|0|integer (-1000-1000)|
|hpYPos|Health Bar Y Position.|0|integer (-1000-1000)|
|hpShowHearts|Show Hearts.|true|boolean|
|hpAlarmVolume|Low HP Alarm Volume.|10|integer (0-10)|
|hpXScale|Health Bar X Scale.|100|integer (-1000-1000)|
MP Bar:

|Name|Description|Default|Type|
|---|---|---|---|
|mpXPos|Magic Bar X Position.|0|integer (-1000-1000)|
|mpYPos|Magic Bar Y Position.|0|integer (-1000-1000)|
|mpXScale|Magic Bar X Scale.|100|integer (-1000-1000)|

Drive Bar:

|Name|Description|Default|Type|
|---|---|---|---|
|dpXPos|Drive Bar X Position.|0|integer (-1000-1000)|
|dpYPos|Drive Bar Y Position.|0|integer (-1000-1000)|
|dpXScale|Drive Bar X Scale.|100|integer (-1000-1000)|
|dpYScale|Drive Bar Y Scale.|100|integer (-1000-1000)|

Player Skin:

|Name|Description|Default|Type|
|---|---|---|---|
|playerSkinXPos|Player Skin X Position.|0|integer (-1000-1000)|
|playerSkinYPos|Player Skin Y Position.|0|integer (-1000-1000)|

Lock On:

|Name|Description|Default|Type|
|---|---|---|---|
|lockOnXPos|Lock On HP X Position.|0|integer (-1000-1000)|
|lockOnYPos|Lock On HP Y Position.|0|integer (-1000-1000)|
|lockOnHPScale|Lock On HP Bar Scale.|70|integer (-1000-1000)|
|lockOnIconScale|Lock On Icon Scale.|75|integer (-1000-1000)|
|lockOnIconRotation|Lock On Icon Rotation Speed.|16|integer (-1000-1000)|
|lockOnHpPerBar|Lock On HP per bar.|40|integer (10-100)|

Party:

|Name|Description|Default|Type|
|---|---|---|---|
|partyXPos|Party HUD X Position.|0|integer (-1000-1000)|
|partyYPos|Party HUD Y Position.|0|integer (-1000-1000)|
|partyYOffset|Party HUD Y Offset.|60|integer (-1000-1000)|

Focus:

| Name        | Description           | Default | Type                 |
| ----------- | --------------------- | ------- | -------------------- |
| focusXPos   | Focus HUD X Position. | 0       | integer (-1000-1000) |
| focusYPos   | Focus HUD Y Position. | 0       | integer (-1000-1000) |
| focusXScale | Focus Bar X Scale.    | 100     | integer (-1000-1000) |
| focusYScale | Focus Bar Y Scale.    | 100     | integer (-1000-1000) |

