# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- Town view with three buildings:
  - Town Gate: pick a battlefield
  - Wizard's Tower: spend experience on max mana and mana regeneration
  - Market: buy bones with gold (10 gold each); bought bones go to the next battle and come back if unused
- Three maps: Hillside (ward along one edge), Crossroads (wizard in the middle, enemies from every side), Outpost (outpost on one edge, enemies from three sides)
- Terrain: boulders block walking, swamp slows it
- Summons:
  - Wisp (10 mana): floats through terrain and moves diagonally; fights alone, but heals other summons when they are around
  - Skeleton Warrior (5 mana + 1 bone): sturdy melee
  - Skeleton Archer (10 mana + 2 bones): shoots from two tiles, slow and fragile
- Enemies and drops:
  - Kobold: weak and fast; always 1 bone, 10 % chance of 1 gold; all kobolds flee for 1 s when one dies
  - Goblin: 50 % chance of 1-2 bones, 20 % chance of 1-2 gold; panics when four fall within 5 s unless an orc is within 3 tiles
  - Orc: strong and slow; 50 % chance of 1-3 bones, 25 % chance of 2-5 gold
- Waves: kobolds only in waves 1-2, goblins from wave 3, orcs from wave 5, tight packs from wave 10
- End-of-battle tally: 0.5 / 1 / 2 exp per kobold / goblin / orc, +0.01 exp per unused field bone, multiplied by the wave reached (0.2x for waves 1-3, 0.5x 4-10, 0.7x 11-20, 1.0x 21-40, 1.2x 41-60, then +0.2x per 20 waves), rounded up
- Progress (gold, exp, stored bones, upgrades) is saved in the browser's local storage
- Background music with a mute toggle

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood", made by the project owner with Suno.
