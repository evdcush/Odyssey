### Pairing portals
To set up pairs of Nether portals properly so that they reliably travel to each other, it is best to build both portals manually. Build at desired location X,Y,Z in the Overworld. Then travel to the Nether. And then dig your way to X/8, Y, Z/8, and build a portal there. 

As block coordinates are centered on the lower northwest corner of blocks, higher precision can be achieved by placing a portal in the nether where block coordinates are the least precise relative to the Overworld, recording the block coordinates, and adding 0.5 to each value before multiplying it by 8 to find the ideal Overworld coordinates. This can allow portals as close as 8 blocks to behave reliably in the Overworld, and can make adjacent portal blocks in the nether reliably teleport to different overworld portals as well.  Even greater precision can be achieved when considering that teleportation from the Nether to the Overworld uses the player's coordinates without rounding -- thereby making it possible to have reliable, if difficult to use, portals as close as 1 block. Precisely linked portals can also be stacked vertically without interfering with one another.  

A less precise method would be to temporarily deactivate all portals within a 128 block "radius" from within the Nether. Through death or with the aid of a second player, entering a new portal from the Overworld forces the creation of a new portal within the Nether which the overworld portal should prefer. This is not recommended as it limits how close overworld portals can be placed due to the zone of exclusions and can lead to unpredictable placement of the resulting portal.

The Y coordinate is not divided for pairings, however it does play a factor in mapping the portals. Therefore, two overworld portals could be built at the same x,z coordinates with one at a very low Y, e.g., 5, and one at a higher y, e.g. 160.  A Nether portal at these X and Z coordinates links to whichever portal is closest on the Y axis.

If this all sounds complicated to you, this website can help you in the process: https://gamertools.net/applications/nether.

### Zones of exclusion
The nether portal spawning algorithm can only spawn a portal within a 33×33 block column centered on the destination, but it does scan that width (and the height of the world) for open space to place the portal. This often causes it to spawn a portal at a location significantly different than the corresponding location in the other world. The larger the distance between a portal and its "ideal" destination, the larger the zone of exclusion. This zone is the area in each world where you cannot build another portal without breaking the link between the first two portals. One way to think of this zone is as spheres around each portal, each of a true radius equal to its distance to the equivalent location of the other. For example, if the overworld portal was at (0,50,0) and the Nether portal at (0,100,0), then the portals are 50 meters away from each other. In this (simple) case, if a nether portal was built closer than 50 meters to (0,50,0), then the Overworld portal links to it.  

Because of the coordinate change, portals created in the Nether are much more likely to have ideal coordinates that are horizontally distant from the overworld portal that created them. When going the other way, horizontal coordinates tend to be closer to ideal (because whatever space is found has a Nether-equivalent location closer to the original portal), but vertical displacement can still be an issue.   

If you wish to ensure that two portals link together, manually build portals as close as possible in all 3 coordinate axes. It doesn't have to be exact, or even all that close, if the player ensures that no other portals is constructed in the exclusion zone created by the difference.

### 2-in-1 Nether portals
It is possible to end up in a situation where a nether portal "randomly" places the player in 1 of 2 possible overworld destination portals. This is simply because the nether portal has two effective coordinates as it is 2 blocks wide, say (X, Y, Z) on the left, and (X+1, Y, Z) on the right. If the player entered on the left side, (X, Y, Z) translates to (X*8, Y, Z*8) in the overworld and the game picks the portal closest to that. If the player entered on the right side, (X+1, Y, Z) translates to (X*8+8, Y, Z*8) and the game picks a portal closest to that point instead. This situation occurs when the nether portal's location is roughly equidistant between the 2 overworld portals (within 8 blocks overworld distance difference). However, building 2 nether portals side by side is probably better for destination clarity than building a 2-in-1 portal. It is possible to span distances with pairs of portals in this way, though normally faster to simply walk through the Nether.[1]
