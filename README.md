This page is incomplete. The following readme is a mockup for a Patapon Randomizer setup.
## Setup
Download the following two files from the [Releases page in Github](putlinkhere):
- patapon.yaml
- patapon.apworld

Get PPSSPP, the PSP emulator.
???

Then, follow the below steps to setup the randomizer:

### YAML configuration
The first thing you need to do is configure the patapon.yaml file. For that, open and
edit the YAML to fit whatever settings you want to play with:
- name: Enter your desired slot name here, could be almost anything. {player} or {PLAYER} are replaced with the slot number, while {number} or {NUMBER} will increment once for each duplicate YAML name.
- goal: Can be All Bosses, Gong, and Gorl, in all bosses you need to beat all bosses and raise them to the boss goal level, in gong mode you need to progress to Gong Vows to Fight and clear the mission, and in gorl mode you need to clear the mission "Servant of Darkness".
- all_bosses_goal: Int, 1-50, default is 4. This is the level all bosses need to be before your game is cleared. This does nothing in other modes.
- mission_order: Can be Vanilla, Shuffle, Progressive, and Completely Random, Vanilla does not change the mission order, Shuffle missions are in a random order in which you can beat them, Progressive missions are story order missions sent through Archipelago, Completely Random mode are random ordered missions sent through Archipelago.
- progressive_mission_amount: Int, 0-16, represents the percent of filler items that are replaced with progressive mission checks for the progressive mission order mode. This does nothing in other modes.
- kaching_gather_step: Int, 50-500. Changes how much total kaching gathered is needed to send out an item. Default is 150.
- kaching_gather_count: Int, 0-80. Changes how many kaching steps exist. Default is 40. Setting this 0 disables these filler checks.
- missionsanity: Adds all mission clears as locations. This also adds equipment into the loot pool based on one of the best items from that mission.
- tipsanity: Adds random tips from loading screens as items as locations. Adds equipment and materials into the loot pool based on tips. (+20 filler checks)
- matersanity: Adds first times creating units as locations. Adds materials into the loot pool. (+27 filler checks)
- randomize_buildings: Adds Mater and the Altar as locations and to the item pool. Can be Vanilla, Shuffle, Completely Random. In vanilla, buildings are found in their usual location. In Shuffle, buildings are shuffled between their usual locations. In Completely Random, buildings can be anywhere.
- randomize_commands: Can be Vanilla, Shuffle, Completely Random. In vanilla, commands are found in their usual location. In Shuffle, All commands OTHER THAN MARCH+ATTACK are shuffled between their usual locations. In Completely Random, All commands OTHER THAN MARCH+ATTACK can be anywhere.
- randomize_miracle_inputs: Slightly more technical and only changes gameplay. Miracles play a total of 8 command patterns, each with their own pattern IDs. In Vanilla, these are completely untouched. In Shuffle, miracle pattern IDs are shuffled. In Random, miracle patterns are randomly generated. In Completely Random, Shuffle and Random rules apply.
- randomize_drums: Randomizes the locations of Chaka and Don drums. Vanilla does not randomize, Shuffle moves each one to their own location, Completely Random puts it in the Archipelago item pool. 
- randomize_boss_maps: Some bosses in Patapon are only found from having their map item in your inventory. Vanilla does not randomize, Shuffle moves them between their respective locations, Completely Random puts them in the Archipelago item pool. 
- randomize_miracles: Miracles are necessary to complete some missions in the game. Logically, you should be able to obtain some miracles some time before their required missions. Vanilla does not randomize, Shuffle moves them between their respective locations, Completely Random puts them in the Archipelago item pool. 
- randomize_WEP_totems: Randomize items from WEP totems. Vanilla does not randomize, Shuffle moves them between their respective locations, Completely Random puts them in the Archipelago item pool.
- randomize_memories: Randomizes the locations of unit memories for creation at Mater. Vanilla does not randomize, Shuffle moves them between their respective locations, Completely Random puts them in the Archipelago item pool. 
- randomize_minigames: Randomizes minigame locations. Vanilla does not randomize, Shuffle moves them between their respective locations, Completely Random puts them in the Archipelago item pool. 
- pakapon_minigame: Int, 0-10. Adds checks to the Pan Pakapon minigame. Also adds random stones and woods to the item pool.
- zakpon_minigame: Int, 0-10. Adds checks to the Fah Zakpon minigame. Also adds random vegetables to the item pool.
- gashapon_minigame: Int, 0-10. Adds checks to the Rah Gashapon minigame. Also adds random stews to the item pool.
- kimpon_minigame: Int, 0-10. Adds checks to the Kon Kimpon minigame. Also adds random stones to the item pool.
- kampon_minigame: Int, 0-10. Adds checks to the Ton Kampon minigame. Also adds random alloys to the item pool.
- kampon_weapon_minigame: Int, 0-10. Adds checks to the weapon version of the Ton Kampon minigame. Also adds divine weapons to the item pool.
- randomize_armor_stats: Armor gain new stats. Vanilla does nothing, Keep BST takes the total stat amount and randomizes them into new stats, Shuffle swaps all armor base stats, Completely Random makes all stats random.
- randomize_weapon_stats: Weapons gain new stats. Vanilla does nothing, Keep BST takes the total stat amount and randomizes them into new stats, Shuffle swaps all weapon base stats, Completely Random makes all stats random.
- randomize_rarepon_stats: Rarepons gain new stats. Vanilla does nothing, Keep BST takes the total stat amount and randomizes them into new stats, Shuffle swaps all rarepon base stats, Completely Random makes all stats random.
- randomize_rarepon_palettes: Recolors rarepons. Vanilla does nothing, Shuffle swaps them between each other, completely random makes up new colors for all.
    - Trap weights replace a percentage of the filler pool as negative effects.
- grass_trap_weight: Adds grass which spawns on Hatapon if mid-mission.
- leaf_trap_weight: Trap that causes the player to gain a leaf. It doesn't do anything, but its there!
- sleep_trap_weight: Trap that causes all patapons to become drowsy in a mission. 
- stagger_trap_weight: Trap that causes all patapons to become staggered in a mission.
- tumble_trap_weight: Trap that causes all patapons to become tumbled in a mission.
- additional_npc_trap: Adds unused NPCs to the item pool. They don't do anything except make you look into the development history of Patapon. (+3 traps)
- randomize_music: Randomizes what music plays in each mission.
- item_receive_sound: play a sound when receiving an archipelago item. Maybe make this one customizable?
- death_link: Can be 'true' or 'false', when true turns on death link. When a mission is failed through abandonment, hatapon's death, zero units remaining or a scripted loss, a death link is sent. When a death link is received in a mission, Hatapon dies. When a death link is received in Patapolis, a festival stops if it is ongoing.

### Multiworld generation
Once your YAML is configured, navigate to your Archipelago installation folder (will vary
depending on where you installed Archipielago, but an example path would be
C:\ProgramData\Archipelago). In the Players folder paste your YAML file as well as the
YAMLs of any other players participating in the multiworld. In the lib/worlds folder, paste
patapon.apworld. Then open the archipelago launcher and click Generate. This will
generate a .zip in the Output folder found in your archipelago installation, in the same path
where the players folder is. Once the generation finishes, unpack the zip to get your patch file 
for your Patapon world, then navigate to [the archipelago](https://archipelago.gg) website, 
click on get started, then click Host Game, then "Upload File" and select the zip
folder in the Output subfolder of your Archipelago folder. The game will generate along with
the Spoiler log. Click on Create New Room and that’s done! The Archipelago server is now
running!

### Setting up the mod
Archipelago supports patching games through the launcher. 
Use the "Open Patch" feature on the left side of the archipelago launcher and select your patch file. 
If this is your first time setting it up, you will need to select your copy of Patapon and your PPSSPP installation afterwards. 
This will set up Open Patch to open your Patapon worlds in the future. PPSSPP should automatically open and your game
roster will have a Patapon game with a special archipelago icon on the bottom left corner 
along with your player slot name and generation date in DD/MM/YY.

## Locations and items
In multiworld games setups, locations are the places you need to go to unlock new things.
In Patapon, there are locations customizable in your yaml.
- Total Kaching gathered in steps.
- Altar introduction cutscene.
- Mater introduction cutscene.
- Doing missions for the first time.
- New unit creation.
- Viewing new tips.
- Finding:
  - Commands
  - Drums
  - Boss Maps
  - Miracles
  - WEP totem items
  - Memories
  - Minigames
- Doing minigames.

The items are:
- Commands
- Drums
- Boss Maps
- Miracles
- WEP totem items
- Memories
- Minigames
- Mater
- Altar
- Missions
- Unique Equipment
- Filler
  - Materials
  - Armor
  - Weapons
  - Ka-ching
  - Potions
  - Hunting Missions Rewards
- Traps
  - Grass
  - Leaf
  - Sleep
  - Stagger
  - Tumble
  - NPCs
