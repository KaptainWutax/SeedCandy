# SeedCandy 

This project is a free and open-source standalone tool which offers various tweaks and operations that can be done to (partial) Minecraft seeds. 

### Downloads

You can find downloads for SeedCandy on the [GitHub releases page](https://github.com/WearBlackAllDay/SeedCandy/releases). 


---

### DungeonCracker
This tab finds possible StructureSeeds (**NOT** a WorldSeed) based on information about a dungeon.
-  GUI
	- left click: toggle mossy/cobble
	- right click: toggle known/unknown
	- orientation: north is upwards
- Inputfields
	- size: dimension of your dungeonfloor (including the blocks hidden below walls)
	- x, y, z: coordinates of the spawner block (f3 "looking at")
	- version: minecraft-version the dungeon was **generated** in (this might be lower than the worlds/servers version)
	- biome: the biome the dungeon is in (only relevant for 1.16 dungeons)
	- "010101...": string representation of the dungeonfloor (should only be edited if you wish to enter manual data)
- Buttons
	- "move": jumps over to the StructureSeed tab and carries the latest results over
	- "copy": copies all results to clipboard
	- "bits/32": displays the bits of information you have currently collected and starts the cracking process (if this has no output, your data is flawed and if it has your dungeon data is correct, but the version can still be wrong)

### StructureSeed
This tab finds possible WorldSeeds from StructureSeeds and offers to check WorldSeeds for Biome-restrictions.
- input
	- manually enter or paste in your seed(s) line per line
	- avoid whitespaces if possible
- biome entry
	- enter coordinates and type of biome you wish to check for / know about
	- when cracking a WorldSeed 5-6 entries are sufficient
	- rows left blank are ignored
- buttons
	- "reverse to nextLong()": outputs **maximum** 2 WorldSeeds per StructureSeed, assuming the world was randomly generated. This does **not** require any biome-entries, but can fail if the seed was manually entered.
	- "crack with biomes": scans all possible WorldSeeds from input (65536 per StructureSeed) and returns results that match the specified biome-criteria (might take a few seconds, but will **not** miss a WorldSeed)
	- "verify WorldSeeds": performs the same operation, but on a WorldSeed (no SisterSeeds are used)

### WorldSeed
This tab offers various operations that can be done to get information about your WorldSeed.

- input
	- manually enter or paste in your seed(s) line per line
	- avoid whitespaces if possible
- buttons
	- "check for nextLong()": outputs whether a seed can be randomly generated by Minecraft or not
	- "locate Quadhuts": scans seeds for quadruple-WitchHuts (~2 seconds per seed, multithreaded for multiple entries)
	- "show/filter Spawnpoint": if no coordinates are specified, will output the spawn coordinates of a seed, if coordinates are entered will only return seeds with matching spawnpoint (can be slow, multithreaded for multiple entries)
	- "convert to hash":outputs the SHA2-representation of the seed
	- "switch to ShadowSeed":outputs the shadow of the seed (same biomes, different everything else)
	- "get SisterSeeds"outputs the 65536 sisters of the seed (same structures and nether, different biomes; can take a while for a long list of seeds due to size of the output)
	- "reduce to StructureSeed": outputs the lower 48 bits (StructureSeed) of the seed that only contain information about structures (can output itself if the upper 16 bits are 0)
	- "copy Output": copies the output to the clipboard
	- "clear text": removes all text from both fields
	- "get any other type of Seed": if you need those, odds are you know what you are doing ;)

---

### License

SeedCandy is licensed under MIT, a free and open-source license. For more information, please read the [license file](https://github.com/WearBlackAllDay/SeedCandy/blob/master/LICENSE).
