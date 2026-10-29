# The Summonancer

Version 0.8.10-alpha · see [CHANGELOG.md](CHANGELOG.md)

An incremental browser game about a wizard who summons skeletons (summons, not raises) to hold back goblins, gathers resources and builds up a city.

## Play

Open `index.html` in a browser. No build step, no install.

Current prototype:
- A new game starts in the middle of a battle on the Hillside with only wisps. Back in town the wizard talks to himself, the Builder (still alive, hard hat and all) builds the Summoning Septagram for free, and skeletons are bound there with the bones from that first battle. After that the Builder turns up as a skeleton and asks about a dental plan.
- Older saves skip the introduction and keep wisps, skeletons and archers
- Town view with the wizard standing in town (he blinks out when you head for battle and reappears when you come back) and these buildings:
  - Town Gate: pick a battlefield
  - Spelltower: spend experience on max mana, mana regeneration and summon slots (5 at start, then 25 / 50 / 75 / 100 / 150 exp, +50 per slot after that)
  - Builder: spend gold to put up new buildings: Summoning Septagram (free), Cryptic Laboratory and Wisping Well (40 gold), Golematorium (100 gold + 10 each of smooth stone, scrap iron and wood), Marketplace (30), Overdue Library (60), Protective Stone Circle (50), Archivus Arcanus (150)
  - The Summoning Septagram ("Pentagrams are for amateurs, Hexagrams are for nerds!"): binds each kind of summon once. Wisp is free, Skeleton Warrior 5 bones, Skeleton Archer 15 bones + 15 gold, Golem 60 gold + 1 skull
  - The Golematorium: golem research (Living Quarry for health and size, Granite Skin, Ground Slam, Seismic Tempo for a slam every 3rd and then every 2nd attack, Rumbling Presence, Pebble Legs)
  - The Overdue Library ("Please return all spells by the due date. Fines are payable in souls."): learn new spells (Firebolt, 80 gold), longer and cheaper Command and Nemesis, and Exposed (the marked enemy takes more damage)
  - Marketplace ("Everything has a price. Mostly a bad one."): sell 10 bones for 1 gold, a skull or crystal shard for 5, 5 stone/iron/wood for 1; buy bones for 1 gold each, skulls and crystal shards for 50, stone/iron/wood for 10
  - Protective Stone Circle ("Stonehenge? We just keep our sheep penned here..."): a sturdier ward, the Shove spell (pushes nearby enemies back, every 60 s down to 30 s) and Mending Stones
  - Archivus Arcanus: "You are not prepared!"
  - The upgrade buildings show each summon's animation and current numbers
  - Cryptic Laboratory ("It's not a crypt! It's a Laboratory!"): skeleton research for damage, attack speed, move speed, armor, health and, for archers, range (up to twice the reach at level 10), Piercing Arrows (up to a 50 % chance an arrow goes on to the next enemy behind) and Flaming Arrows (every 5th arrow can set the enemy alight)
  - Wisping Well ("Drop a coin in the well and you probably just lose a coin."): wisp research for shorter swamp daydreams, faster healing, self-mending, damage, health and speed
  - Research costs gold, plus bones from level 2 and skulls from level 6
  - Tavern: where villagers hand out quests and pay for finished ones, in two lists. Story Quests: the first, "So you wanna be a hero?", asks for 20 kobolds and pays 25 gold and 25 exp. Common Quests: 2-3 jobs the villagers make up, new after every battle (reach a wave on a field, defeat enemies on a field, bring back resources, break the enemy ward on Assault), with their own explanations and the wizard's replies; up to three at once; rewards of 20-150 exp and goods worth 20-100 gold at Marketplace prices. The Quests button in the top bar lists active and finished quests and shows a gold "!" when one is ready to hand in
  - Warehouse: everything carried back from battle, grouped (basics, materials, forged, mushrooms, trophies), as compact pixel-art icons (gold, bones, skulls, smooth stone, scrap iron, wood, crystal shards); the same icons are used for every price, reward and tally, with the name on hover or tap
  - Spellbook: choose which known spells go into battle. Every spell takes a slot, Command and Nemesis included (Move and Shove don't). 3 slots to start; the Spelltower sells a 4th, 5th and 6th for 1000 gold + 50 crystal shards, 3000 + 150 and 8000 + 400
  - Saina's Wagon: Saina Lot, skeleton bard and bookkeeper, turns up after the fifth battle and keeps the ledger (battles, gold and exp earned, everything gathered, foes defeated by kind, summons called, longest stands, Assault victories, furthest Gauntlet runs, Raid chiefs). She has something to say every time you visit, and drops hints about what to do next
  - Spirit Stones (the Wisping Well's second tier, shown inside the well, 150 gold + 20 smooth stone + 10 crystal shards, once a spirit is bound): spirit health, armour, speed, damage, Phasing (10 levels, untouchable for 0.1-1.0 s after a hit) and Regeneration (1 / 2 / 3 HP every 5 s)
  - Blacksmith (150 gold + 30 smooth stone + 20 wood): a work queue that runs in real time, in battle and while the game is closed. Charcoal (1 wood, 1 s), iron ingots (5 scrap iron + 1 wood, 2 s), steel ingots (1 iron ingot + 1 wood + 5 charcoal, 5 s). Any amount or Max; orders can count on what earlier jobs will make; jobs can be paused, removed and reordered (the piece on the anvil is handed back). Spending anything the queue still needs (Marketplace, buildings, research, bindings, spells, slots, skills) asks first
  - The Chrono Crystal (1000 gold + 100 crystal shards): a Speed button on every battlefield toggles double speed
  - Invisible Academy (300 gold + 200 smooth stone + 20 iron ingots, after the Blacksmith): learn skills once and choose which ones each summon uses; one skill slot each, more from the summon's own building (Smarter Skeletons 1000 gold + 1000 bones + 100 skulls, Deeper Thoughts for golems 1000 gold + 100 stone + 100 scrap iron + 50 crystal shards). Skills: Pseudo Reality (wisps and spirits, learned separately: 10 % of physical attacks miss, up to 20 % with Barely There), Rapid Slash (skeletons: every 5th hit, the next 3 come 75 % faster), Flaming Arrows and Frost Arrows (archers: every 5th arrow burns or slows 60 % for 6 s), Ground Slam (golems). Skills are improved in the Laboratory and the Golematorium
  - Equipment (tap the wizard in town): head, torso, cloak, arms, hands, feet, staff, neck and two rings. Raid chiefs drop pieces of their hall's set (common / uncommon / rare / legendary, 1-3 bonuses: max mana, mana regeneration, summon slots, summon damage and health, cheaper spells, ward, battle gold and exp, crystal and skull chance). What he wears shows on him. Five sets with bonuses at 2 / 3 / 5 pieces: Ember Regalia (kobolds), Frostbound Attire (trolls), Definitely Not a Necromancer's Outfit (goblins), Stonewarden's Garb (ogres) and Warlord's Hand-Me-Downs (orcs; 5 pieces: summons move 50 % faster while the Nemesis target lives). Spare pieces sell at the Marketplace
  - The Grand Grimoire of Everything (also opens from the book button in the top bar, which pauses a battle while it's open): Enemies pages fill in as enemies are defeated (what they drop is the last page, at 300 defeats), Allies pages as summons are called (1 / 5 / 15 / 30 / 60 defeats unlock appearance and walk, combat stats with stand and attack animations, drops and rewards, behaviour with the panic animation, and field notes with the charmed and confused animations)
- Gauntlet: a cave with walls on three sides, a 3 x 3 ward at the bottom, a great gate at the top and four side gates that light up before enemies walk in. Defeat 30 / 60 / 100 (Easy / Normal / Hard) and the great gate opens; the summons rush through, the wizard teleports and the next cave is harder. Summons, mana and loot carry on, the ward gets half its strength back, and the rewards for every cave cleared are paid when the run ends
- Raid: a brick hall with a 5 x 6 carpet in the colours and emblem of whoever lives there (kobolds, goblins, orcs, ogres or trolls). Beat the guards from the side gates and the chief (Kobold King, Goblin Boss, Orc Warlord, Ogre Chieftain, Troll Elder) walks down the carpet. Beat it for the victory, a reward and at least one piece of equipment
- Move (Gauntlet and Raid): the ward and the wizard shuffle a tile a second toward the spot you tap; only the wizard's own tile must be clear (the ward may slide over walls, rocks and stalagmites, but not over a gate); free, but no summoning while it moves; an enemy in the way dents the ward
- Four maps: Hillside (ward along one edge), Crossroads (wizard in the middle, enemies from every side), Outpost (outpost on one edge, enemies from three sides) and Assault (break the red enemy ward at the top; enemies pour out of it; the ward is armoured, wisps barely scratch it, it pulses to hurt summons right next to it and every third of its health lost it releases a squad of defenders; Easy / Normal / Hard change its health, the time between waves and enemy strength; summons with nothing close to fight march up and attack it; spells that hit a tile can't touch it)
- Quests also ask for ogres and trolls (once you have met them), caves cleared in the Gauntlet, Raid chiefs and summoning a number of one kind in a single battle (Bob doesn't believe you can)
- Each battle generates a fresh field: grass, dirt, sand, rock, boulders, swamp, bushes, trees, puddles, lakes (2-9 tiles in a 3x3 area) and sometimes a river crossing the whole field with 1-3 bridges. Every walkable tile is guaranteed to connect to the ward.
  - Sand and puddles slow a little, swamp a lot, bushes slow enemies only
  - Boulders, trees, lakes and rivers block walkers; wisps float over everything
  - Grass, bushes and trees are flagged flammable and dirt diggable for future spells
- Retreat button (tap twice to confirm): leave a battle early and keep everything gathered so far; the wizard goes through his defeat animation and blinks back to town
- Spells: Command (10 mana, every summon heads to a tile for 1 s), Nemesis (20 mana, every summon attacks one marked enemy for 5 s) Shove once the Stone Circle teaches it, Firebolt once learned at the Library (2 mana, 1 damage on one tile; grass and bushes burn for 8 s and trees for 30 s, then turn to dirt; anything walking through the flames burns for 5 s, takes 1 damage a second and panics unless it's a summon; summons step out of fire and route around it, golems don't burn) Guardstone (100 gold + 5 crystal shards to learn, 10 mana: a crystal with a glowing circle 2 tiles around it; the first summon to step inside stays on guard, wanders the circle, fights anything that comes within 3 tiles and walks back afterwards; one stone at a time, a new one replaces the old; Library upgrades: more guards per stone, a wider circle, more stones, armour and mending for guards inside the circle) Freeze (100 gold + 5 crystal shards to learn, 25 mana: a ring of cold chills everything in a 3 x 3 area, 60 % slower for 5 s, and puts out fires except burning trees; skeletons and wisps are immune; Library upgrades: a larger area, up to 85 % slower, down to 10 mana and up to 10 s) and Nurture (200 gold + 50 wood to learn, 10 mana: bare or burnt earth grows into grass, grass into a bush and a bush into a tree, unless the tree would block the last way to the ward)
- The wizard is on the battlefield: at the bottom of the Hillside, inside the ward elsewhere. He casts when you summon or cast, flinches when the ward is hit and cheers when a wave is cleared. When the ward falls a raincloud forms over him, lightning strikes beside him, it rains on his hat and he blinks back to town.
- Steering movement: units keep their momentum between targets, turn at a limited rate (about 90° in a quarter second), slow down in sharp turns, reach full speed in 0.8 s and brake in 0.3 s when they hold still
- Summons:
  - Wisp (10 mana): floats through terrain and moves diagonally; fights alone, but heals other summons when they are around; 2 % chance per second to wander off for 10 s when a swamp is within 3 tiles
  - Skeleton Warrior (5 mana + 1 bone): sturdy melee
  - Skeleton Archer (10 mana + 2 bones): shoots from two tiles, slow and fragile
  - Golem (20 mana + 3 bones, takes two summon slots): slow and very tough; nearby enemies attack it instead; punches three times with one fist, then a ground slam hits everything in front of it and shoves it back
  - Spirit (25 mana, bound for 200 gold + 10 skulls + 10 crystal shards): drifts through anything and hovers on top of enemies, hurting everything underneath; at half health it falls back to the nearest wisp (or the ward) and returns at 80 %; doesn't burn or freeze; wards take half damage from it
- Enemies and drops:
  - Every bone drop has a small chance (kobold 1 %, goblin 2 %, orc 3 %) to be a whole skull instead
  - Kobold: weak and fast; always 1 bone, 25 % chance of 1 gold; all kobolds flee for 1 s when one dies
  - Goblin: 50 % chance of 1-2 bones, 35 % chance of 1-3 gold; panics when four fall within 5 s unless an orc is within 3 tiles
  - Orc: strong and slow; 50 % chance of 1-3 bones, 50 % chance of 3-6 gold
  - Ogre (from wave 17): 70 health, hits for 6; every 6th or 7th blow is a ground slam that hits every summon around and shoves them back; never panics, burns but keeps going; keeps goblins steady like an orc; more gold, iron and stone, 4 % skull, 4 % crystal
  - Troll (from wave 20): 70 health, hits for 5; mends 1 health every 5 s unless it is burning; fire hurts it twice as much and it panics from it; bones, wood and gold, rarely a skull or crystal
- Waves: kobolds only in waves 1-2, goblins from wave 3, orcs from wave 5, tight packs from wave 10; from wave 40 every wave adds 3 % to enemy health and damage (wave 50: +33 %)
- Mushrooms (red, blue, yellow, green), pouches of sand and one trophy per enemy (kobold scales, goblin claws, orc hairs, ogre toenails, troll teeth, about 5 %), saved for alchemy and gear upgrades still to come
- Materials for things still to come, kept in the warehouse: smooth stone (kobolds 8 %, orcs 10 %), scrap iron (goblins 10 %, orcs 15 %), wood (kobolds 6 %, goblins 8 %) and crystal shards (kobolds 1 %, goblins 2 %, orcs 3 %)
- End-of-battle tally: 0.5 / 1 / 2 exp per kobold / goblin / orc, multiplied by the wave reached (0.5x for waves 1-3, 0.75x 4-6, 0.9x 7-9, 1.0x 10-19, 1.1x 20-39, 1.2x 40-59, then +0.2x per 20 waves), rounded up
- Progress (gold, exp, warehouse, buildings, research, upgrades, grimoire) is saved in the browser's local storage
- Background music (two tracks in turn) with a mute toggle
- Sound effects synthesised with Web Audio (no sound files): attacks, summoning, deaths, the falling ward, teleports and coins, with their own on/off toggle

All tunable values live in the `DATA` object at the top of the script.

Design decisions are kept in the design document; code lives here.

## Music

`music/ghost_of_sherwood.mp3` – "Ghost of Sherwood" and `music/shadowy_loops.mp3` – "Shadowy Loops", both made by the project owner with Suno.

## Developer console

The DEV button in the town view sets exp and every resource (as a grid of icons), resets upgrades, fills the Grimoire, unlocks everything or starts a new game. It is for testing and will be removed before release.

## Character art

`style-studies/newcast.html` studies the four newest characters (ogre, troll, spirit, Saina Lot). `style-studies/bestiary.html` shows every enemy (kobold, goblin, orc, ogre, troll) with all animations, each attack move, randomly rolled looks and the crowned Raid chiefs, using the game's own drawing code. `style-studies/cast.html` is the animated character study (the wizard with beard stages, gear sets, levitation and teleport sequences; skeleton, archer, wisp, golem, goblin, kobold, orc) with walk, stand, attack, panic, charmed and confused animations and per-character random looks. The same drawings are used in the Grimoire and on the battlefield. The "Art" button in battle switches between the new art and the original classic shapes; the choice is remembered.
