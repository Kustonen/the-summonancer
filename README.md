# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- Grid battlefield with boulders (block movement) and swamp (slows movement)
- Mana that regenerates over time
- Skeleton Warrior summoning (5 mana + 1 bone) in the lit rows near the ward
- Bog Goblin waves that drop bones
- Smooth movement with A* pathfinding around terrain

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.
