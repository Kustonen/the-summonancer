# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- Grid battlefield with boulders (block movement) and swamp (slows movement)
- Mana that regenerates over time
- Two summons: Wisp (10 mana, floats through terrain, weak hits) and Skeleton Warrior (5 mana + 1 bone)
- Three maps: Hillside (ward along one edge), Crossroads (wizard in the middle, goblins from every side), Outpost (outpost on one edge, goblins from three sides)
- Bog Goblin waves that drop bones
- Smooth movement with A* pathfinding around terrain

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood", made by the project owner with Suno.
