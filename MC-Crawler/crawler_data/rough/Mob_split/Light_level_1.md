## Internal light level
Internal sky light versus time and sky light
The internal light level is used for calculations within the game. The game uses the internal light level of one block to compute aspects of the game, which include mob spawning, plant growth, and daylight detector outputs.

The game uses sky light, time, and weather to calculate an internal sky light value (also known as darkening sky light), then uses the maximum level of the block light and the internal sky light to calculate the internal light (formula: (max(internal sky light,block light))). This value is an integer with a maximum level of 15; it can also be negative.

Here are the levels of internal sky light at a sky light of level 15:


| Internal sky light | Clear                                                                                          |                                                        | Rain or snowfall |                                                                             | Thunder                                   |                                                                                                                            |
|--------------------|------------------------------------------------------------------------------------------------|--------------------------------------------------------|------------------|-----------------------------------------------------------------------------|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
|                    | Time↓                                                                                          | Time↑                                                  | Time↓            | Time↑                                                                       | Time↓                                     | Time↑                                                                                                                      |
| 4                  |                                                                                                | 13,670–(Midnight/18,000)-22,330(8,660 Gtk/7:13)        |                  | 13,670–(Midnight/18,000)-22,330(8,660 Gtk/7:13)                             |                                           | 13,670–(Midnight/18,000)-22,330(8,660 Gtk/7:13)                                                                            |
| 5                  | 22,331–22,491(160 Gtk/8 sec)                                                                   | 13,509–13,669(160 Gtk/8 sec)                           | 22,331–22,565()  | 13,436–13,669()                                                             | 22,331–22,671()                           | 13,330–13,669()                                                                                                            |
| 6                  | 22,492–22,652(160 Gtk/8 sec)                                                                   | 13,348–13,508(160 Gtk/8 sec)                           | 22,566–22,798()  | 13,203–13,435()                                                             | 22,672–23,010()                           | 12,990–13,329()                                                                                                            |
| 7                  | 22,653–22,812‌[JE  only]<br/>22,653–22,813‌[BE  only]J: (159 Gtk/7.95 sec)B: (160 Gtk/8 sec)   | 13,188–13,347(159 Gtk/7.95 sec)                        | 22,799–23,031()  | 12,969–13,202()                                                             | 23,011–23,352()                           | 12,648–12,989()                                                                                                            |
| 8                  | 22,813‌[JE  only]–22,973<br/>22,814‌[BE  only]–22,973J: (160 Gtk/8 sec)B: (159 Gtk/7.95 sec)   | 13,027–13,187(160 Gtk/8 sec)                           | 23,032–23,266()  | 12,734–12,968()                                                             | 23,353–23,700()                           | 12,300–12,647()                                                                                                            |
| 9                  | 22,974–23,134(160 Gtk/8 sec)                                                                   | 12,867–13,026(159 Gtk/7.95 sec)                        | 23,267–23,504()  | 12,497–12,733()                                                             | 23,701-(Dawn/24,000/0)–59(240 Gtk/12 sec) | 11,941‌[JE  only]–(Dusk/12,000)-12,299<br/>11,942‌[BE  only]–(Dusk/12,000)-12,299J:(358 Gtk/17.9 sec)B:(357 Gtk/17.85 sec) |
| 10                 | 23,135–23,296(161 Gtk/8.05 sec)                                                                | 12,705–12,866(161 Gtk/8.05 sec)                        | 23,505–23,745()  | 12,256–12,496()                                                             |                                           | 60–(Noon/6,000)-11,940‌[JE  only]<br/>60–(Noon/6,000)-11,941‌[BE  only]J: (11,880 Gtk/9:54)B: (11,881 Gtk/9:54)            |
| 11                 | 23,297–23,459(162 Gtk/8.1 sec)                                                                 | 12,542–12,704(162 Gtk/8.1 sec)                         | 23,746–23,991()  | 12,010–12,255()                                                             |                                           | N/A                                                                                                                        |
| 12                 | 23,460–23,623‌[JE  only]<br/>23,460–23,624‌[BE  only]J: (163 Gtk/8.15 sec)B: (164/8.2 sec)     | 12,377–12,541(164 Gtk/8.2 sec)                         |                  | 23,992–(Dawn/24,000/0)(Noon/6,000)(Dusk/12,000)-12,009(12,017 Gtk/10:00.85) |                                           | N/A                                                                                                                        |
| 13                 | 23,624‌[JE  only]–23,790<br/>23,625‌[BE  only]–23,790J: (166 Gtk/8.3 sec)B: (165 Gtk/8.25 sec) | 12,210–12,376(166 Gtk/8.3 sec)                         |                  | N/A                                                                         |                                           | N/A                                                                                                                        |
| 14                 | 23,791–23,960(169 Gtk/8.45 sec)                                                                | 12,041–12,209(168 Gtk/8.4 sec)                         |                  | N/A                                                                         |                                           | N/A                                                                                                                        |
| 15                 |                                                                                                | 23,961–(Dawn/24,000/0)(Noon/6,000)(Dusk/12,000)-12,040 |                  | N/A                                                                         |                                           | N/A                                                                                                                        |

To obtain an internal sky light for a sky light level s less than 15, take the internal level L at 15 and subtract from it the difference between 15 and s: L−(15−s).

| Icon  | Time                           | Internal sky light when sky light is 15 |
|-------|--------------------------------|-----------------------------------------|
|       | noon, during clear weather     | 15                                      |
| <br/> | noon, duringrainorsnowfall     | 12                                      |
|       | noon, during athunderstorm     | 10[storm 1]                             |
|       | midnight, during clear weather | 4                                       |

1. ↑During thunderstorms, hostile mobs are allowed to spawn as if the internal sky light level were actually 5.

### Effects of internal light
Keep in mind that the internal light level is only one of the considerations that apply to mob spawning and plant growth.

#### Mobs
| Light level > Mob v                         | 0                             | 1 | 2 | 3                | 4 | 5 | 6 | 7                                                                          | 8 | 9 | 10 | 11                                         | 12 | 13 | 14 | 15                                                            |
|---------------------------------------------|-------------------------------|---|---|------------------|---|---|---|----------------------------------------------------------------------------|---|---|----|--------------------------------------------|----|----|----|---------------------------------------------------------------|
| Bats                                        |                               |   |   | Spawn at y: 0–62 |   |   |   | Spawn at y: 0–62 from October 20 to November 3‌[JE  only]                  |   |   |    |                                            |    |    |    | Do not spawn                                                  |
| Blazes                                      |                               |   |   |                  |   |   |   |                                                                            |   |   |    | Spawn innether fortresses                  |    |    |    | Do not spawn                                                  |
| Wither skeletons                            |                               |   |   |                  |   |   |   | Spawn innether fortresses                                                  |   |   |    |                                            |    |    |    | Do not spawn                                                  |
| Zombified piglins                           |                               |   |   |                  |   |   |   |                                                                            |   |   |    | Spawn inthe Nether                         |    |    |    | Do not spawn                                                  |
| Slimes(slime chunk)                         |                               |   |   |                  |   |   |   |                                                                            |   |   |    |                                            |    |    |    | Spawn in slime chunks at Y: -64–40                            |
| Slimes(swamp)                               |                               |   |   |                  |   |   |   | Spawn in swamp biomes at Y: 50–70                                          |   |   |    |                                            |    |    |    | Do not spawn                                                  |
| Skeletons                                   | Spawn in theOverworld         |   |   |                  |   |   |   | Spawn in the Nether                                                        |   |   |    | Do not spawn                               |    |    |    | Do not spawn, burn insunlight                                 |
| Zombies<br/>Chicken jockeys                 | Spawn in theOverworld         |   |   |                  |   |   |   |                                                                            |   |   |    | Do not spawn                               |    |    |    | Do not spawn, burn insunlight                                 |
| Drowned                                     | Spawn inoceansandrivers       |   |   |                  |   |   |   |                                                                            |   |   |    | Hostile, do not spawn                      |    |    |    | Burn insunlight, ignore player outside water when in sunlight |
| Creepers<br/>Witches                        | Spawn in the Overworld        |   |   |                  |   |   |   |                                                                            |   |   |    |                                            |    |    |    | Do not spawn                                                  |
| Phantoms                                    |                               |   |   |                  |   |   |   | Spawn in the Overworld if player hasn't entered abedin over 3 in-game days |   |   |    | Do not spawn                               |    |    |    | Burn insunlight                                               |
| Spiders<br/>Cave spiders<br/>Spider jockeys | Spawn in the Overworld        |   |   |                  |   |   |   |                                                                            |   |   |    | Hostile, do not spawn                      |    |    |    | Do not spawn,neutralunless provoked                           |
| Silverfish                                  |                               |   |   |                  |   |   |   |                                                                            |   |   |    | Spawn frommonster spawnersin the Overworld |    |    |    | Hostile, do not spawn                                         |
| Endermen                                    | Spawn in all three dimensions |   |   |                  |   |   |   | Spawn inthe Nether                                                         |   |   |    |                                            |    |    |    | Do not spawn, teleport randomly in Overworld                  |
