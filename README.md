# The Summonancer

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- A new game starts in the middle of a battle on the Hillside with only wisps. Back in town the wizard talks to himself, the Builder (still alive, hard hat and all) builds the Summoning Septagram for free, and skeletons are bound there with the bones from that first battle. After that the Builder turns up as a skeleton and asks about a dental plan.
- Older saves skip the introduction and keep wisps, skeletons and archers
- Town view with the wizard standing in town (he blinks out when you head for battle and reappears when you come back) and these buildings:
  - Town Gate: pick a battlefield
  - Spelltower: spend experience on max mana, mana regeneration and summon slots (5 at start, then 25 / 50 / 75 / 100 / 150 exp, +50 per slot after that)
  - Builder: spend gold to put up new buildings: Summoning Septagram (free), Cryptic Laboratory and Wisping Well (40 gold), Golematorium (100), Overdue Library (60), Protective Stone Circle (50), Archivus Arcanus (150)
  - The Summoning Septagram ("Pentagrams are for amateurs, Hexagrams are for nerds!"): binds each kind of summon once. Wisp is free, Skeleton Warrior 5 bones, Skeleton Archer 15 bones + 15 gold, Golem 60 gold + 1 skull
  - The Golematorium: golem research (Living Quarry for health and size, Granite Skin, Ground Slam, Rumbling Presence, Pebble Legs)
  - The Overdue Library ("Please return all spells by the due date. Fines are payable in souls."): longer and cheaper Command and Nemesis, and Exposed (the marked enemy takes more damage)
  - Protective Stone Circle ("Stonehenge? We just keep our sheep penned here..."): a sturdier ward, the Shove spell (pushes nearby enemies back, every 60 s down to 30 s) and Mending Stones
  - Archivus Arcanus: "You are not prepared!"
  - The upgrade buildings show each summon's animation and current numbers
  - Cryptic Laboratory ("It's not a crypt! It's a Laboratory!"): skeleton research for damage, attack speed, move speed, armor and health
  - Wisping Well ("Drop a coin in the well and you probably just lose a coin."): wisp research for shorter swamp daydreams, faster healing, self-mending, damage, health and speed
  - Research costs gold, plus bones from level 2 and skulls from level 6
  - Warehouse: everything carried back from battle (gold, bones, skulls)
  - The Grand Grimoire of Everything (also opens from the book button in the top bar, which pauses a battle while it's open): Enemies pages fill in as enemies are defeated, Allies pages as summons are called (1 / 5 / 15 / 30 / 60 defeats unlock appearance and walk, combat stats with stand and attack animations, drops and rewards, behaviour with the panic animation, and field notes with the charmed and confused animations)
- Three maps: Hillside (ward along one edge), Crossroads (wizard in the middle, enemies from every side), Outpost (outpost on one edge, enemies from three sides)
- Each battle generates a fresh field: grass, dirt, sand, rock, boulders, swamp, bushes, trees, puddles, lakes (2-9 tiles in a 3x3 area) and sometimes a river crossing the whole field with 1-3 bridges. Every walkable tile is guaranteed to connect to the ward.
  - Sand and puddles slow a little, swamp a lot, bushes slow enemies only
  - Boulders, trees, lakes and rivers block walkers; wisps float over everything
  - Grass, bushes and trees are flagged flammable and dirt diggable for future spells
- Spells: Command (10 mana, every summon heads to a tile for 1 s), Nemesis (20 mana, every summon attacks one marked enemy for 5 s) and Shove once the Stone Circle teaches it
- The wizard is on the battlefield: at the bottom of the Hillside, inside the ward elsewhere. He casts when you summon or cast, flinches when the ward is hit and cheers when a wave is cleared. When the ward falls a raincloud forms over him, lightning strikes beside him, it rains on his hat and he blinks back to town.
- Steering movement: units keep their momentum between targets, turn at a limited rate (about 90° in a quarter second), slow down in sharp turns, reach full speed in 0.8 s and brake in 0.3 s when they hold still
- Summons:
  - Wisp (10 mana): floats through terrain and moves diagonally; fights alone, but heals other summons when they are around; 2 % chance per second to wander off for 10 s when a swamp is within 3 tiles
  - Skeleton Warrior (5 mana + 1 bone): sturdy melee
  - Skeleton Archer (10 mana + 2 bones): shoots from two tiles, slow and fragile
  - Golem (20 mana + 3 bones): slow and very tough; nearby enemies attack it instead, and its ground slam hits everything in front of it and shoves it back
- Enemies and drops:
  - Every bone drop has a small chance (kobold 1 %, goblin 2 %, orc 3 %) to be a whole skull instead
  - Kobold: weak and fast; always 1 bone, 10 % chance of 1 gold; all kobolds flee for 1 s when one dies
  - Goblin: 50 % chance of 1-2 bones, 20 % chance of 1-2 gold; panics when four fall within 5 s unless an orc is within 3 tiles
  - Orc: strong and slow; 50 % chance of 1-3 bones, 25 % chance of 2-5 gold
- Waves: kobolds only in waves 1-2, goblins from wave 3, orcs from wave 5, tight packs from wave 10
- End-of-battle tally: 0.5 / 1 / 2 exp per kobold / goblin / orc, multiplied by the wave reached (0.5x for waves 1-3, 0.75x 4-6, 0.9x 7-9, 1.0x 10-19, 1.1x 20-39, 1.2x 40-59, then +0.2x per 20 waves), rounded up
- Progress (gold, exp, warehouse, buildings, research, upgrades, grimoire) is saved in the browser's local storage
- Background music (two tracks in turn) with a mute toggle
- Sound effects synthesised with Web Audio (no sound files): attacks, summoning, deaths, the falling ward, teleports and coins, with their own on/off toggle

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood" and `music/shadowy_loops.mp3` – "Shadowy Loops", both made by the project owner with Suno.

## Developer console

The DEV button in the town view sets exp, gold, bones and skulls, resets upgrades, fills the Grimoire, unlocks everything or starts a new game. It is for testing and will be removed before release.

## Character art

`style-studies/cast.html` is the animated character study (the wizard with beard stages, gear sets, levitation and teleport sequences; skeleton, archer, wisp, golem, goblin, kobold, orc) with walk, stand, attack, panic, charmed and confused animations and per-character random looks. The same drawings are used in the Grimoire and on the battlefield. The "Art" button in battle switches between the new art and the original classic shapes; the choice is remembered.
