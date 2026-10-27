# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- Three maps: Hillside (ward along one edge), Crossroads (wizard in the middle, enemies from every side), Outpost (outpost on one edge, enemies from three sides)
- Terrain: boulders block walking, swamp slows it
- Summons:
  - Wisp (10 mana): floats through terrain and moves diagonally; fights alone, but heals other summons when they are around
  - Skeleton Warrior (5 mana + 1 bone): sturdy melee
  - Skeleton Archer (10 mana + 2 bones): shoots from two tiles, slow and fragile
- Enemies:
  - Bog Goblin: panics for 1-5 s when four goblins fall within 5 s, unless an orc is within 3 tiles
  - Kobold: weaker and faster, drops 1 bone; all kobolds flee for 1 s when one dies
  - Orc: strong and slow, steadies nearby goblins
- Small first waves (2, 2, 3 enemies), then +2 per wave; kobolds from wave 2, orcs from wave 4
- Background music with a mute toggle

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood", made by the project owner with Suno.
