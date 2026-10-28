# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- Town view with three buildings:
  - Town Gate: pick a battlefield
  - Spelltower: spend experience on max mana, mana regeneration and summon slots (5 at start, then 25 / 50 / 75 / 100 / 150 exp, +50 per slot after that)
  - Market: buy bones with gold (10 gold each); bought bones go to the next battle and come back if unused
  - The Grand Grimoire of Everything (also opens from the book button in the top bar, which pauses a battle while it's open): a bestiary that fills in as enemies are defeated (1 / 5 / 15 / 30 / 60 defeats unlock appearance and walk, combat stats with stand and attack animations, drops and rewards, behaviour with the panic animation, and field notes with the charmed and confused animations)
- Three maps: Hillside (ward along one edge), Crossroads (wizard in the middle, enemies from every side), Outpost (outpost on one edge, enemies from three sides)
- Each battle generates a fresh field: grass, dirt, sand, rock, boulders, swamp, bushes, trees, puddles, lakes (2-9 tiles in a 3x3 area) and sometimes a river crossing the whole field with 1-3 bridges. Every walkable tile is guaranteed to connect to the ward.
  - Sand and puddles slow a little, swamp a lot, bushes slow enemies only
  - Boulders, trees, lakes and rivers block walkers; wisps float over everything
  - Grass, bushes and trees are flagged flammable and dirt diggable for future spells
- Spells: Command (10 mana, every summon heads to a tile for 1 s) and Nemesis (20 mana, every summon attacks one marked enemy for 5 s)
- Steering movement: units keep their momentum between targets, turn at a limited rate (about 90° in a quarter second), slow down in sharp turns, reach full speed in 0.8 s and brake in 0.3 s when they hold still
- Summons:
  - Wisp (10 mana): floats through terrain and moves diagonally; fights alone, but heals other summons when they are around; 2 % chance per second to wander off for 10 s when a swamp is within 3 tiles
  - Skeleton Warrior (5 mana + 1 bone): sturdy melee
  - Skeleton Archer (10 mana + 2 bones): shoots from two tiles, slow and fragile
- Enemies and drops:
  - Kobold: weak and fast; always 1 bone, 10 % chance of 1 gold; all kobolds flee for 1 s when one dies
  - Goblin: 50 % chance of 1-2 bones, 20 % chance of 1-2 gold; panics when four fall within 5 s unless an orc is within 3 tiles
  - Orc: strong and slow; 50 % chance of 1-3 bones, 25 % chance of 2-5 gold
- Waves: kobolds only in waves 1-2, goblins from wave 3, orcs from wave 5, tight packs from wave 10
- End-of-battle tally: 0.5 / 1 / 2 exp per kobold / goblin / orc, +0.01 exp per unused field bone, multiplied by the wave reached (0.5x for waves 1-3, 0.75x 4-6, 0.9x 7-9, 1.0x 10-19, 1.1x 20-39, 1.2x 40-59, then +0.2x per 20 waves), rounded up
- Progress (gold, exp, stored bones, upgrades) is saved in the browser's local storage
- Background music with a mute toggle

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood", made by the project owner with Suno.

## Developer console

The DEV button in the town view sets exp and gold and resets Spelltower abilities. It is for testing and will be removed before release.

## Character art

`style-studies/cast.html` is the animated character study (skeleton, archer, wisp, goblin, kobold, orc) with walk, stand, attack, panic, charmed and confused animations and per-character random looks. The same drawings are used in the Grimoire and on the battlefield. The "Art" button in battle switches between the new art and the original classic shapes; the choice is remembered.
