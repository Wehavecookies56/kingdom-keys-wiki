---
{"dg-publish":true,"permalink":"/config/client-config/"}
---


Here you'll find all client options which don't affect gameplay, server cannot enfoce those.

General:

| Name              | Description                                                  | Default | Type    |
| ----------------- | ------------------------------------------------------------ | ------- | ------- |
| summonTogether    | Summon both Keyblade and Armor with Summon Keyblade key.     | false   | boolean |
| auto3rdPersonShip | Automatically change to 3rd person when riding a gummi ship. | true    | boolean |

HUD Data: These ones don't matter much in the config, they are changed from inside the game.

| Name              | Description                               | Default                                       | Type        |
| ----------------- | ----------------------------------------- | --------------------------------------------- | ----------- |
| cmHUDData         | Command Menu HUD Data                     | [5.0, 5.0, 70.0, 75.0, 1.0, 1.0, 0.0, 6.0]    | float array |
| rcHUDData         | Reaction Commands HUD Data                | [5.0, 80.0, 100.0, 16.0, 1.0, 1.0, 0.0, 6.0]  | float array |
| hpHUDData         | Health Bar HUD Data                       | [13.8, 3.8, 916.0, 254.0, 0.2, 0.2, 0.0, 8.0] | float array |
| mpHUDData         | Magic Bar HUD Data                        | [53.0, 8.6, 142.0, 12.0, 0.7, 0.5, 0.0, 8.0]  | float array |
| driveHUDData      | Drive Bar HUD Data                        | [53.7, 14.6, 95.0, 18.0, 0.8, 0.8, 0.0, 8.0]  | float array |
| portraitHUDData   | Portrait HUD Data                         | [28.0, 18.0, 32.0, 32.0, 0.7, 0.7, 0.0, 8.0]  | float array |
| lockOnHUDData     | Lock On HUD Data                          | [2.0, 2.0, 166.0, 40.0, 0.7, 0.7, 0.0, 2.0]   | float array |
| partyHUDData      | Party HUD Data                            | [3.0, 0.0, 25.0, 120.0, 1.0, 1.0, 0.0, 5.0]   | float array |
| focusHUDData      | Focus Bar HUD Data                        | [3.0, 27.0, 66.0, 40.0, 1.0, 1.0, 0.0, 8.0]   | float array |
| munnyExpHUDData   | Munny get and Exp for next level HUD Data | [0.0, 0.0, 80.0, 60.0, 1.0, 1.0, 0.0, 0.0]    | float array |
| levelUpHUDData    | Level up notification HUD Data            | [1.0, 10.0, 155.0, 50.0, 1.0, 1.0, 0.0, 2.0]  | float array |
| driveLevelHUDData | Drive level HUD Data                      | [0.0, -4.0, 155.0, 90.0, 1.0, 1.0, 0.0, 3.0]  | float array |


GUI:

| Name           | Description                                                                                      | Default | Type    |
| -------------- | ------------------------------------------------------------------------------------------------ | ------- | ------- |
| showGuiToggle  | Toggle HUD visibility. Weapon option only shows while holding a Keyblade or Organization weapon. | SHOW    | enum    |
| customFont     | Enable the custom font                                                                           | true    | boolean |
| showDriveForms | Drive Forms Visibility.                                                                          | true    | boolean |

Command Menu:

| Name                        | Description                                                      | Default           | Type                 |
| --------------------------- | ---------------------------------------------------------------- | ----------------- | -------------------- |
| cmChangeColor               | Allow the Command Menu to change colors based on nearby enemies. | true              | boolean              |
| magicDisplayedInCommandMenu | Magic displayed in the Magic submenu.                            | list of magic IDs | list                 |
| cmTextXOffset               | Command Menu Text X Offset.                                      | 0                 | integer (-1000-1000) |
| cmHeaderTextVisibility      | Command Menu Header Text Visibility.                             | true              | boolean              |
| cmClassicColors             | Command Menu classic color scheme.                               | false             | boolean              |
| cmSelectedXOffset           | Command Menu Selected X Offset.                                  | 5                 | integer (-1000-1000) |
| cmSubXOffset                | Command Menu Submenu X Offset %.                                 | 100               | integer (-1000-1000) |
| cmEndLWidth                 | Command Menu Element Left End Segment Width.                     | 10                | integer (0-256)      |
| cmEndRWidth                 | Command Menu Element Right End Segment Width.                    | 10                | integer (0-256)      |
| cmHeaderEndLWidth           | Command Menu Header Left End Segment Width.                      | 10                | integer (0-256)      |
| cmHeaderEndRWidth           | Command Menu Header Right End Segment Width.                     | 15                | integer (0-256)      |
| cmReactionEndLWidth         | Reaction command left end segment width.                         | 10                | integer (0-256)      |
| cmReactionEndRWidth         | Reaction command right end segment width.                        | 10                | integer (0-256)      |

HP Bar:

| Name          | Description          | Default | Type                 |
| ------------- | -------------------- | ------- | -------------------- |
| hpShowHearts  | Show Hearts.         | true    | boolean              |
| hpAlarmVolume | Low HP Alarm Volume. | 10      | integer (0-10)       |

Lock On:

| Name               | Description                  | Default | Type                 |
| ------------------ | ---------------------------- | ------- | -------------------- |
| lockOnIconScale    | Lock On Icon Scale.          | 75      | integer (-1000-1000) |
| lockOnIconRotation | Lock On Icon Rotation Speed. | 16      | integer (-1000-1000) |
| lockOnHpPerBar     | Lock On HP per bar.          | 40      | integer (10-100)     |

Party:

| Name         | Description           | Default | Type                 |
| ------------ | --------------------- | ------- | -------------------- |
| partyYOffset | Party HUD Y Offset.   | 60      | integer (-1000-1000) |


