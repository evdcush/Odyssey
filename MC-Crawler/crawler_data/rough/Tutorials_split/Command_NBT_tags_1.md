### Blocks
These tags are put on blocks as items.

| Tagname        | Description                                                                                                                                                                                                                                                 | Value Type                                                                                                                                                                                                                                 | Example                                                                                                                  |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| CanPlaceOn     | This tag is used when making adventure maps to determine which block(s) the player can place a block on. Also used on hoes to make them till dirt and on spawn eggs to place them.  If the value is not a valid block or item it displays as "`missingno`". | An array of strings, each one of which is a command argument of typeblock_predicate. However, to use NBT tags, the NBT data of the block must be synchronized to the client (campfires and player heads are two of the blocks that do so). | `{CanPlaceOn:["minecraft:stone","#minecraft:logs","minecraft:player_head[rotation=8]{SkullOwner:{Name:'Dinnerbone'}}"]}` |
| BlockEntityTag | This is used for tile entities, and stores their data for when they are placed down                                                                                                                                                                         | Differs based on the block, seeTutorials/Command NBT tags § Blocks 2for details. Example: get a white shield by using a command:`/give @p shield{BlockEntityTag:{Base:0}}`                                                                 | `{BlockEntityTag:{Glowing:1b}}`                                                                                          |
| BlockStateTag  | This tag is used for blocks, and stores the block state when they are placed down.                                                                                                                                                                          | A compound where each key is a block state key, and the value is the block state value to force place for this block. Differs based on the block, seeBlock statesfor details.                                                              | `{BlockStateTag:{facing:"west",half:"top",shape:"straight"}}`                                                            |

## Entities
These tags are used when using the /summon command to spawn entities or when using the /data to edit the data of entities.

| NBT Tag             | Description                                                                                                                                                                                                                                                                                                                                                                                                                            | Allowed tagnames                                                                                                                                                                                                                          | Required tagnames                                                                                 | Syntax                                                                                                                                               |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| TileEntityData      | Used to store all data kept within a block. Mainly used within blocks that can store items or contain various data values, e.g., Command blocks, Chests, Jukeboxes, Dispenser, Beacon, etc.                                                                                                                                                                                                                                            | CustomName, Items, Command, Levels, Primary, Secondary, Delay, MaxNearbyEntities, MaxSpawnDelay, MinSpawnDelay, RequiredPlayerRange, SpawnCount, SpawnRange, EntityID                                                                     | None                                                                                              | `{TileEntityData:{Entity NBT data here}}`                                                                                                            |
| Motion              | Determines theinitialvelocity of most entities (all other than Dragon Fireballs, Fireballs, Small Fireballs and Wither Skulls) upon being summoned. Must be entered as double precision floating point values (decimals). Example: {Motion:[0.0,1.0,0.0]} summons with an initial upward velocity of 1.0. The values could be only -10 to 10, because it could have been to be moved very fast. It normally could lead to a wall clip. | n/a                                                                                                                                                                                                                                       | All                                                                                               | `{Motion:[DOUBLE,DOUBLE,DOUBLE]}`                                                                                                                    |
| direction           | Similar to Motion, determines theinitialvelocity of Dragon Fireballs, Fireballs, Small Fireballs, and Wither Skulls upon being summoned. This tag isrequiredto summon said entities, otherwise the command fails. Example: {direction:[0.0,1.0,0.0]} summons with an initial upward velocity of 1.0.This tag determines only the entity's velocity, not the direction that it's facing.                                                | n/a                                                                                                                                                                                                                                       | All                                                                                               | `{direction:[DOUBLE,DOUBLE,DOUBLE]}`                                                                                                                 |
| power               | Similar to direction, but determines constant acceleration. Example: {power:[0.0,1.0,0.0]} gives the summoned entity a constant upward acceleration of 1.0.  Entities are still affected by drag when power is nonzero and eventually reaches a terminal velocity. Affects only Dragon Fireballs, Fireballs, Small Fireballs, and Wither Skulls.                                                                                       | n/a                                                                                                                                                                                                                                       | All                                                                                               | `{power:[DOUBLE,DOUBLE,DOUBLE]}`                                                                                                                     |
| ActiveEffects       | Sets the effects that apply to a mob after it is summoned. Type999999to apply its countdown toinfinity. It should hide its numbers to *.                                                                                                                                                                                                                                                                                               | Id, Duration, Amplifier, Ambient, ShowParticles                                                                                                                                                                                           | All                                                                                               | `{ActiveEffects:[{Id:INT,Duration:INT,Amplifier:BYTE,Ambient:BYTE,ShowParticles:BYTE,ShowIcon:BYTE}, ...]}`                                          |
| rewardExp           | Controls villagers giving xp for trading, set to true or false. Normally, villagers can reward you experience orbs.                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                           | True/False                                                                                        | `{rewardExp:BYTE}`(`0b`for false or`1b`for true)                                                                                                     |
| Passengers          | Sets which entities are ridingon top ofthe base entity.  Allows multiple entities to ride one base entity. Riding entities are still able to do all stuff they have coded.Like enemies shooting on each other etc.Do not use a recent mob (if it doesn't exist in your old version Minecraft).                                                                                                                                         | all (not checked)                                                                                                                                                                                                                         | id                                                                                                | `{Passengers:[{id:STRING, ...}, ...]}`                                                                                                               |
| ArmorItems          | Defines what items are being worn by the mob. Items go in slots Feet, Legs, Chest, Head, in that order.                                                                                                                                                                                                                                                                                                                                | Item                                                                                                                                                                                                                                      | None                                                                                              | `{ArmorItems:[{Count:BYTE,id:STRING,tag:{...}},{Count:BYTE,id:STRING,tag:{...}},{Count:BYTE,id:STRING,tag:{...}},{Count:BYTE,id:STRING,tag:{...}}]}` |
| HandItems           | Defines what item is within the mainhand and offhand. First item is the mainhand, second is offhand.                                                                                                                                                                                                                                                                                                                                   | Item                                                                                                                                                                                                                                      | None                                                                                              | `{HandItems:[{Count:BYTE,id:STRING,tag:{...}},{Count:BYTE,id:STRING,tag:{...}}]}`                                                                    |
| HandDropChances     | Determines how likely it is for an entity to drop held Items. The tag Count in the equipment tag must be 1 or greater for this to work.                                                                                                                                                                                                                                                                                                | 2 separate float values, one for the main hand and one for the off-hand slot. 0.0-1.0 determines likelihood of dropping, but applies a random durability if it does. Anything greater than 1.0 makes it always drop with full durability. | Since it is a float value, it must be phrased as "X.Y", with X and Y being values of your choice. | `{HandDropChances:[FLOAT,FLOAT]}`                                                                                                                    |
| ArmorDropChances    | Determines how likely it is for an entity to drop worn Items. The tag Count in the equipment tag must be 1 or greater for this to work.                                                                                                                                                                                                                                                                                                | 4 separate float values, one for each slot. 0.0-1.0 determines likelihood of dropping, but applies a random durability if it does. Anything greater than 1.0 makes it always drop with full durability.                                   | Since it is a float value, it must be phrased as "X.Y", with X and Y being values of your choice. | `{ArmorDropChances:[FLOAT,FLOAT,FLOAT,FLOAT]}`                                                                                                       |
| NoAI                | Makes mobs have no AI, resulting in mobs not moving on their own. However, they still react to other changes in the environment. For example, theZombiecan still burn in the sun.                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                           |                                                                                                   | `{NoAI:BYTE}`(`0b`for false or`1b`for true)                                                                                                          |
| NoGravity           | Makes mobs unaffected by gravity. Mobs do not fall. Mobs cannot walk in the air.                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                           |                                                                                                   | `{NoGravity:BYTE}`(`0b`for false or`1b`for true)                                                                                                     |
| Silent              | Makes mobs silent. Does not work for certain sounds, seeMC-64242.                                                                                                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                           |                                                                                                   | `{Silent:BYTE}`(`0b`for false or`1b`for true)                                                                                                        |
| Fire                | Determines how many ticks a mob is on fire. When Fire reaches one, the fire stops, and the mob no longer takes damage. When a mob is not on fire, this value is 1.                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                           |                                                                                                   | `{Fire:SHORT}`(ranges from 0 to 32767)                                                                                                               |
| Invulnerable        | Makes mobs invulnerable to everything exceptthe Voidand players inCreative Mode. Mobs do not attack or run away from invulnerable mobs.                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                           |                                                                                                   | `{Invulnerable:BYTE}`(`0b`for false or`1b`for true)                                                                                                  |
| Attributes          | Customizes the attributes of the entity. SeeAttributefor more details                                                                                                                                                                                                                                                                                                                                                                  | Name: seeAttributefor a list. Base: the amount to apply. Modifiers: how much and how it should vary. Contains values Name, Amount, Operation, UUID.                                                                                       | Name and Base                                                                                     | `{Attributes:[{Name:STRING,Base:DOUBLE,Modifiers:[{Name:STRING, Amount:DOUBLE,Operation:BYTE,UUID:[I;INT,INT,INT,INT]}]}`                            |
| Health              | Number of hearts (for hearts above the default maximum you must change the base value of the 'generic.max_health' attribute).                                                                                                                                                                                                                                                                                                          | All Mobs                                                                                                                                                                                                                                  | Number in half hearts                                                                             | `{Health:FLOAT}`                                                                                                                                     |
| AngerTime, AngryAt  | A neutral mob becomes aggressive toward`AngryAt`for`AngerTime`ticks.                                                                                                                                                                                                                                                                                                                                                                   | Summoning neutral mobs                                                                                                                                                                                                                    | Number in ticks, paired with a UUID                                                               | `{AngerTime:INT,AngryAt:[I;INT,INT,INT,INT]}`                                                                                                        |
| CustomName          | Summons a mob with a name that appears above their head.                                                                                                                                                                                                                                                                                                                                                                               | All Mobs                                                                                                                                                                                                                                  | A JSON Text component                                                                             | `{CustomName:'"Custom Name"'}`or you can use{CustomName:'{"text":"Name Here ","color":"blue",...}'}                                                  |
| CustomNameVisible   | Alters the visibility of a custom name. 0b Means that the name is only visible when looking at the mob (default), and 1b means the name is always visible. Must use CustomName JSON code first to perform it.                                                                                                                                                                                                                          | All Mobs                                                                                                                                                                                                                                  | Byte, 0b or 1b                                                                                    | `{CustomNameVisible:BYTE}`(`0b`for false or`1b`for true)                                                                                             |
| PersistenceRequired | Mobs are undisappearable on time. Tamed animals without commands can also evolve this action.                                                                                                                                                                                                                                                                                                                                          | All Mobs                                                                                                                                                                                                                                  | True/False                                                                                        | `{PersistenceRequired:BYTE}`(`0b`for false or`1b`for true)                                                                                           |

The following table provides information on each tagname that can be added in an NBT Tag. These tagnames are specific to the /summon command.

| NBT Tag             | Description                                                                                                                                                                                                                                                                                                                        | Used In                                   | Value Type                                                                                     | Allowed Values                                     |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|------------------------------------------------------------------------------------------------|----------------------------------------------------|
| Type                | Used to change the type of mobs, like horses. Setting a horse's type to 4 makes it a skeleton horse.                                                                                                                                                                                                                               | Summon                                    | Integer                                                                                        | 1 - JavaOverflowLimit                              |
| Saddle              | Used to spawn horses or pigs that have saddles on.                                                                                                                                                                                                                                                                                 | Summon                                    | Boolean Binary                                                                                 | true / false or 1 / 0                              |
| Tame                | Used to spawn tamed horses.                                                                                                                                                                                                                                                                                                        | Summon                                    | Boolean Binary                                                                                 | true / false or 1 / 0                              |
| Variant             | Changes the horse or axolotl variant. Setting no variant or putting an incorrect variant spawns a normal white horse or pink axolotl. SeeHorse Variantsfor the list of horse variants.                                                                                                                                             | Summoning Horses                          | Integer                                                                                        | 1 - 1030                                           |
| Size                | Changes the size of a slime, magma cube or phantom summoned into the game. Anything higher than 255 summons size 255. Anything lower than 0 summons size 0. More than 32 tends to cause extreme lag.(The high size of slime or magma cube may gotta lead to a crash. Things on your world won't be saved if you restart the game.) | SummoningSlimes                           | Integer                                                                                        | 0 - 255                                            |
| BlockState          | Determines which block is being summoned when using /summon Falling_block. UseData valuesto find out the ID of each block. You can also use F3+H in-game to show the ID's of items in-game.                                                                                                                                        | Summoning Falling_block (AKA Fallingsand) | Block ID and Block States e.g.`{BlockState:{Name:"minecraft:oak_log", Properties:{axis:"y"}}}` | All Strings                                        |
| Time                | Whether or not the block despawns before hitting the ground. If set to 1 the block falls normally, if set to less than 1 it is set to 0. If set to 0 the block despawns immediately. Recommended to keep this value as 1.                                                                                                          | Summoning Falling_block                   | Integer (Include Negatives)                                                                    | -1 - 127                                           |
| DropItem            | Whether or not the block drops its item form if the block is unable to be placed. If set to 0 the block does not drop its respective item, if set to 1 the block drops its respective item.                                                                                                                                        | Summoning Falling_block                   | Boolean Binary                                                                                 | 0 or 1                                             |
| id                  | Determines the entity the other entity is riding on.                                                                                                                                                                                                                                                                               | Summon                                    | Resource location{id:"minecraft:creeper"}                                                      | Any resource location corresponding to an Entity   |
| Fuse                | Determines how long it takes for PrimedTnt or a Creeper to explode.                                                                                                                                                                                                                                                                | Summon                                    | Short                                                                                          | 0 - 32767                                          |
| ExplosionPower      | Used when summoning fireballs,Withers, andGhaststo set the power of the explosion                                                                                                                                                                                                                                                  | Summon                                    | Integer                                                                                        | 0-127; Beyond 127 no explosion;                    |
| ExplosionRadius     | Used when summoningCreepersto set the radius of the explosion                                                                                                                                                                                                                                                                      | Summon                                    | Byte                                                                                           | 0-127                                              |
| powered             | Determines whether aCreeperis charged or not                                                                                                                                                                                                                                                                                       | Summon                                    | Boolean Binary                                                                                 | 0 or 1                                             |
| PersistenceRequired | Mobs are undisappearable on time. Tamed animals without commands can also evolve this action.                                                                                                                                                                                                                                      | Summon                                    | True/False                                                                                     | {PersistenceRequired:1} or {PersistenceRequired:0} |
| AttachFace          | Determines what face the bottom of the shulker lies on.                                                                                                                                                                                                                                                                            | Summoning Shulkers                        | Byte                                                                                           | 0b - 5b                                            |
| Peek                | Determines how far the Shulkers upper half opens. Positive values make the upper half open with a spin, Negative values appear to make the upper half open without a spin.                                                                                                                                                         | Summoning Shulkers                        | Byte                                                                                           | -127b - 127b                                       |
| APX                 | More information is required on this entry. Appears to be approximated X position.                                                                                                                                                                                                                                                 | Summoning Shulkers                        | Integer                                                                                        | Any whole number                                   |
| APY                 | More information is required on this entry. Appears to be approximated Y position.                                                                                                                                                                                                                                                 | Summoning Shulkers                        | Integer                                                                                        | Any whole number                                   |
| APZ                 | More information is required on this entry. Appears to be approximated Z position.                                                                                                                                                                                                                                                 | Summoning Shulkers                        | Integer                                                                                        | Any whole number                                   |
