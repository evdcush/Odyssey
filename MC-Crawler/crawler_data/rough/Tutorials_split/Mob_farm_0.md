# Tutorials/Mob farm
Mob farms are structures built to acquire mob drops more easily and in larger numbers. They usually consist of two components: a large, dark room to spawn mobs, which are funneled into a central location, and a mob grinder to kill them quickly and efficiently.

## Contents
- 1 Locations
- 2 Drops
- 3 Designs
	- 3.1 Spawning tower
		- 3.1.1 Using observer blocks
	- 3.2 Sinkhole
	- 3.3 Canal-style
		- 3.3.1 Compact canal design
		- 3.3.2 Minimal canal design
		- 3.3.3 Large chamber fully automatic design
		- 3.3.4 Water pans
	- 3.4 Active mob displacement
	- 3.5 Other designs
- 4 Transporting mobs
	- 4.1 Horizontal transportation
	- 4.2 Downward transportation
	- 4.3 Upward transportation
- 5 Grinding
- 6 Video
- 7 Performance concerns

## Locations
The purpose for the farm is to provide a large area that is a viable spawn position for the intended targets, and to kill the mobs quickly. Due to the rules Minecraft applies to spawning mobs, this makes the choice of a location for the mob farm a difficult problem.

Farms placed on the surface can provide good drop rates during the day, when it is one of the few spots of dark ground, but has a sharp drop in effectiveness during nighttime, when the entire surface is dark enough to support mob spawning.

Farms built underground have a time-independent drop rate, and remain within your personal spawn range for hostiles when you go mining, but their effectiveness depends on the amount of unlit caverns in your vicinity, which provide alternative places for mobs to spawn.

Farms floating high in the sky can achieve the best spawn rates during the day and night and you are far away from caves, as they represent the only viable spawn ground. However, building one in survival is rather dangerous, and due to their height they stop working completely when you descend underground to mine resources. To produce loot, you must stay at the height of the farm.

Farms constructed under an ocean can provide the best during day and night, as the ocean limits the viable spawn locations to open areas underground except for drowned, which spawn underwater. You can also locate your base below it to ensure that you are always close enough to spawn monsters. 

Superflat worlds provide higher spawn rates than other worlds, as the missing air pockets underground reduce the amount of dark places.

The Nether is difficult to farm, as water evaporates and most mobs are immune to fire. This reduces the amount of functioning farm designs considerably. One could try to funnel the mobs through Nether Portals to circumvent the restrictions.

## Drops
What a mob farm produces depends on location and the type of grinder used to kill the mobs. Automatic killing prevents certain drops and experience, but is safer as the player is not required to be near the mobs. The following is a table of mobs that can be effectively farmed and their usual and player-caused drops. Player-caused drops and experience can be obtained only when the monster is killed directly by the player or a tamed wolf.

Note that zombie, skeleton, and creeper heads drop only if killed by a charged creeper. Wither skeletons, however, have a small chance to drop theirs no matter the cause of death, but still always drop them when killed via charged creeper.

| Mob              | Normal drops                                                                                                                                                                                        | Player-caused drops                                                                                                                                              | Spawn                                                                                                                                                             | Notes                                                                                                                                                                                                                                       |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Blaze            | None                                                                                                                                                                                                | Blaze Rod                                                                                                                                                        | SpawnsinNether fortressesand at spawners.                                                                                                                         |                                                                                                                                                                                                                                             |
| Cave Spider      | String                                                                                                                                                                                              | Spider Eye                                                                                                                                                       | Spawnsatmonster spawnersinMineshafts.                                                                                                                             | Wall climbing may clog passages.<br/>Can fit through spaces 0.5 blocks tall.                                                                                                                                                                |
| Creeper          | Gunpowder<br/>Music Discs<br/>Creeper Head                                                                                                                                                          | None                                                                                                                                                             | Spawnsin theOverworldwhen dark.                                                                                                                                   | Music Discs drop only when askeletonorstraykills the creepers, requiring special setup beforehand.                                                                                                                                          |
| Drowned          | Rotten Flesh                                                                                                                                                                                        | Copper Ingot<br/>Nautilus Shell<br/>Fishing RodCarved Pumpkin‌[Java Edition  only]Jack o'Lantern‌[Java Edition  only]                                            | Spawninriversand mostoceanbiomes.                                                                                                                                 | Drowned drop tridents and nautilus shells only if they spawned with these.                                                                                                                                                                  |
| Enderman         | Ender Pearl<br/>Block they hold                                                                                                                                                                     | None                                                                                                                                                             | Spawnsin theOverworldwhen dark, inthe Endand sometimes inthe Nether.                                                                                              | Does not work with most water based farms as it teleports out upon taking damage.<br/>Can break farms with randomly taken or placed blocks.<br/>Best farmed inthe EndorWarped Forest.                                                       |
| Ender Dragon     | None                                                                                                                                                                                                | None                                                                                                                                                             | Spawns in theendwhen the player first enters the end, and can be respawned usingend crystals.                                                                     | At 500 xp per respawned dragon, the Ender Dragon is the largest renewablesource of experiencein the game.<br/>By using an unload chunk and TNT duplication bug, it is possible to farm this on a large scale in certain Minecraft versions. |
| Endermite        | None                                                                                                                                                                                                | None                                                                                                                                                             | Have 5% chance to spawn whenender pearllands.                                                                                                                     | Endermenattempt to kill endermites that spawn from ender pearls.                                                                                                                                                                            |
| Evoker           | Totem of Undying<br/>Ominous Banner                                                                                                                                                                 | Emerald                                                                                                                                                          | Spawnsduringraidsor inwoodland mansions.                                                                                                                          | Evoker can summon evoker fangs orvexes.                                                                                                                                                                                                     |
| Ghast            | Gunpowder<br/>Ghast Tear                                                                                                                                                                            | None                                                                                                                                                             | Spawnsin theNether.                                                                                                                                               |                                                                                                                                                                                                                                             |
| Guardian         | Prismarine Shard<br/>Prismarine Crystals Raw Cod/Cooked Cod if the guardian is killed by fire.                                                                                                      | None                                                                                                                                                             | SpawnsinOcean monuments.                                                                                                                                          |                                                                                                                                                                                                                                             |
| Husk             | Rotten Flesh                                                                                                                                                                                        | Iron Shovel<br/>Iron Sword Random Armor Carved Pumpkin‌[Java Edition  only] Jack o'Lantern‌[Java Edition  only]                                                  | Spawnsin desert biomes.                                                                                                                                           | Husks do not burn in sunlight.<br/>A husk that is submerged in water for 30 seconds converts to a normal zombie.                                                                                                                            |
| Hoglin           | LeatherRaw Porkchop Cooked Porkchop if the hoglin is killed by fire.                                                                                                                                | None                                                                                                                                                             | Spawnsin Crimson Forest biome.                                                                                                                                    | Hoglins avoid warped fungi (including in a flower pot), nether portals, and respawn anchors.                                                                                                                                                |
| Magma Cube       | Magma Cream                                                                                                                                                                                         | None                                                                                                                                                             | Spawnsin theNether.                                                                                                                                               | Magma cubes cannot be hurt byfall damageorburning.                                                                                                                                                                                          |
| Phantom          | None                                                                                                                                                                                                | Phantom Membrane                                                                                                                                                 | Spawnsin the night, rain, or thunderstorm if the player hasn't slept in 3 days.                                                                                   | The phantom is anundeadmob.                                                                                                                                                                                                                 |
| Pillager         | Ominous Banner<br/>Items that drops during raids: ‌[Bedrock Edition  only] Emerald Enchanted Book Iron Pickaxe Iron Axe Iron Shovel Iron Sword Iron Helmet Iron Chestplate Iron Leggings Iron Boots | Crossbow<br/>Arrow‌[Bedrock Edition  only]                                                                                                                       | Spawnsinpatrols, aroundpillager outpostsand duringraids.                                                                                                          | If the player kills a pillager wearing a banner on its head, the player receives theBad Omenstatus effect.                                                                                                                                  |
| Ravager          | Saddle‌[Java Edition  only]                                                                                                                                                                         | Saddle‌[Bedrock Edition  only]                                                                                                                                   | Spawnsduringraids.                                                                                                                                                |                                                                                                                                                                                                                                             |
| Silverfish       | None                                                                                                                                                                                                | None                                                                                                                                                             | Can be farmed atstrongholdspawners.                                                                                                                               | The ability to hide in blocks could potentially damage the farm if it is made ofstone.<br/>They can fit through spaces 0.5 blocks tall.                                                                                                     |
| Skeleton         | Arrow<br/>Bone<br/>Bow<br/>Skeleton Skull                                                                                                                                                           | Bow<br/>Random Armor<br/>Carved Pumpkin‌[Java Edition  only]<br/>Jack o'Lantern‌[Java Edition  only]                                                             | Spawnsin theOverworldwhen dark,Skeleton Dungeonspawner,Soul Sand Valley, and sometimes in thenether fortress.                                                     |                                                                                                                                                                                                                                             |
| Slime            | Slimeball                                                                                                                                                                                           | None                                                                                                                                                             | SpawnsinSwamp biomesor inslime chunksbelow y level 40.                                                                                                            | Large slimes could clog smaller passages.                                                                                                                                                                                                   |
| Spider           | String                                                                                                                                                                                              | Spider Eye                                                                                                                                                       | Spawnsin theoverworldwhen dark or frommonster spawnersinDungeons.                                                                                                 | Wall-climbing can clog up passages.                                                                                                                                                                                                         |
| Stray            | Bone<br/>Arrow Wither Skeleton Skull                                                                                                                                                                | Arrow of Slowness<br/>Bow Carved Pumpkin‌[Java Edition  only] Jack o'Lantern‌[Java Edition  only]                                                                | Spawnsunder the sky inSnowy Tundra,Snowy Mountains,Ice Spikes,Frozen River,Frozen Ocean,‌[BE  only]Deep Frozen Ocean‌[BE  only]andLegacy Frozen Ocean‌[BE  only]. |                                                                                                                                                                                                                                             |
| Vex              | None                                                                                                                                                                                                | None                                                                                                                                                             | Can be summoned byevoker                                                                                                                                          | They are capable offlyingthrough theair, and can freely pass through any block, includingwaterandlava, without taking damage.                                                                                                               |
| Vindicator       | Ominous Banner<br/>Items that drops during raids: ‌[Bedrock Edition  only] Emerald Enchanted Book Iron Pickaxe Iron Axe Iron Shovel Iron Sword Iron Helmet Iron Chestplate Iron Leggings Iron Boots | Axe                                                                                                                                                              | Spawnsinwoodland mansions, duringraidor inpatrols‌[Bedrock Edition  only].                                                                                        | A vindicator named Johnny is hostile to every mob except ghasts and illagers.                                                                                                                                                               |
| Wither Skeleton  | Coal<br/>Bone<br/>Wither Skeleton Skull                                                                                                                                                             | Wither Skeleton Skull<br/>Stone Sword<br/>Carved Pumpkin‌[Java Edition  only]<br/>Jack o'Lantern‌[Java Edition  only]                                            | Spawnsin Nether fortresses. On normal or hard difficulties, thewitherspawns 4 wither skeletons when below half health ‌[Bedrock Edition  only].                   | When wither skeleton attacks an entity, the entity is inflicted with thewither effectfor 10 seconds.                                                                                                                                        |
| Witch            | Glass Bottle<br/>Glowstone Dust<br/>Redstone Dust<br/>Spider Eye<br/>Stick<br/>Sugar<br/>Gunpowder                                                                                                  | Potion of Healing<br/>Potion of Fire Resistance<br/>Potion of Swiftness<br/>Potion of Water Breathing                                                            | SpawnsinSwamp huts, anywhere in theOverworldwhen dark, duringraidsor whenvillagerstruck by lightning.                                                             | Witches cannot opendoorsor usecauldrons.                                                                                                                                                                                                    |
| Zoglin           | Rotten Flesh                                                                                                                                                                                        | None                                                                                                                                                             | Spawnswhen a hoglin has been in theOverworldor the End for 300 game ticks (15 seconds).                                                                           | Zoglins attack everyplayer,armor standand everymobexceptcreepers,charged creepersand other zoglins.                                                                                                                                         |
| Zombie           | Rotten Flesh<br/>Zombie Head                                                                                                                                                                        | Iron Ingot<br/>Carrot<br/>Potato<br/>Iron Shovel<br/>Iron Sword<br/>Random Armor<br/>Carved Pumpkin‌[Java Edition  only]<br/>Jack o'Lantern‌[Java Edition  only] | Spawnsin theOverworldwhen dark, fromZombie Dungeonspawner, duringsiege, or converted fromhusk                                                                     | Baby zombie variant is twice as fast and 1 block tall; azombie farmshould account for this to prevent escapes.<br/>When converteddrowned, they can also dropnautilus shells.                                                                |
| Zombified Piglin | Rotten Flesh<br/>Gold Nugget                                                                                                                                                                        | Gold Ingot<br/>Golden Sword<br/>Carved Pumpkin‌[Java Edition  only]<br/>Jack o'Lantern‌[Java Edition  only]                                                      | Spawnsin the Nether and in the Overworld nearNether Portals, when aPiglinis in the overworld for 15 seconds, or when pig struck bylightning.                      | Baby pigman are twice as fast and 1 block tall, similar to baby zombies.<br/>If a Zombie Pigman dies while targetingthe player, it dropsexperience. This mechanic has been used to create xp farms.                                         |
