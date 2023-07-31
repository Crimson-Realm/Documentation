# Crimson Realm

## Description:
* 

## Main Features:
* [Server Rates](#server-rates)
* [Server Limits](#server-limits)
* [Server Maps](#server-maps)
## Changed Features:
* [Fairy System](#fairy-system)
* [Experience System](#experience-system)
* [Gold System](#gold-system)
* [Damage Handler](#damage-handler)
* [Amplifier System](#amplifier-system)
* [Forging System](#forging-system)
## Extra Features:
* [Miscellaneous Stuff](#misceallaneous-stuff)
* [Chest System](#chest-system)
* [Queue System](#queue-system)
* [Unseal System](#unseal-system)
* [Contract System](#contract-system)
* [Level Contest](#level-contest)

### Server Rates:
* Solo EXP: 
* Party EXP: 
* Fairy EXP: 
* Ship EXP: 
* Drop Rate: 
### Server Limits:
* Player Level: 65
* Fairy Level: 41
* Equipment Socket: 2
### Server Maps:
* Ascaron (+ Region)
* Magic Sea (+ Region)
* Deep Blue (+ Region)
* Forsaken City (1, 2 & 3)
* Dark Swamp (1, 2 & 3)
* Demonic World (1 & 2)
* [Chaos Argent](#chaos-argent)

#### Fairy System:
* Everything is customizable via variables.
* Rations considered "auto" do not need to be in third slot, system will auto detect that fairy is not full and will check if player has an auto ration and will consume it. If it needs more than one ration, it will consume till full.
* Players will need to put skills in order from novice to standard, cannot place standard directly.
* All related texts are now tied to variable for easy modification.
* Configurable maximum level for each kind of fruit (mini, normal, great and improved) with an overall maximum level that cannot be surpassed.
* Fairies do not need to be "married" in order to be considered second generation, automatically all fairies that could be obtained from marriage can use possession skill.
* New fairies (Angela and Angela Jr) are usable, along with new improved fruits and rations.
#### Experience System
* Able to customize all rates from just variables: solo, party and boat experience.
* Removed experience from maps without needing items within inventory.
* Increase rates on a per day basis.
* Able to adjust rates on a per level basis to decrease experience obtained the closer the player is to the level limit. Adjusts automatically when increasing level limit.
#### Gold System
* Sent all gold given through a single function.
  * All sources are categorized and can be added multipliers if wanted.
  * Avoids players getting over the maximum limit and a potential reset to 0.
* Extra functions included to hand out gold on monster kill. This can be enable/disabled and is mostly intended for high rate servers.
  * The amount of gold given is random between a minimum and maximum.
    * This can be multiplied if the monster is under several categories:
      * Normal
      * Special
      * Maze
      * Mini-Boss
      * Boss
    * The percentage of getting gold can be adjusted according to the above caterories.
#### Amplifier System:
* Everything is customizable via variables.
* Can add new amplifiers with a single variable and ItemInfo line.
* Won't allow players to use an amplifier if they already have used one with the same or better bonus.
* Able to adjust each percentage of super and lucky strike for each level bonus.
#### Damage Handler
* Function "after_player_kill_player" has been updated to be customizable.
  * Able to customizable kill feed texts.
  * Able to make kill feed text local or global notices on a per-map basis.
#### Forging System:
* Allow to put level limits on a general level, type (unique, dragon, basic) and individual gems.
* Allow to set the specific success rate percentage for each level on each type: forging gems, combining gems and combining refining gems.
* Allow to modify the success rate for each socket percentage.
* Allow to move gems from one slot to another when empty.
  * If a socket goes emtpy upon gem extraction, the gem in the next socket can be moved down. Example: if socket 1 goes empty upon last gem extraction, gems from socket 2 can be moved to 1 and gems from socket 3 moved to 2.
* Prohibit forging same attribute type gem in a single equipment.
  * Example: cannot forge "Chipped Gem of Rage" if equipment already has "Gem of Rage".
* Set a maximum forge level on equipment.
* Blacksmith's plier are customizable.
  * Can obtain "Refining Gem" upon extraction of gem.
  * Can empty the equipment socket and get all gems in it.
  * Combination of the 2 above.
* All of the above can be customized via variables.
* Several gems are available for usage within the files: normal, unique, dragon, advance, hat, broken, cracked, chipped, great and azrael gems.
#### Chaos Argent:
* The whole map script was cleaned, modified and improved to easier usage and modification with only variables.
* The essence of the map stayed the same, but a lot of improvements were made on the map to increase player engagement.
* New functions were added to handle cheaters like players forming party inside, anti-relog penalties, multi-account prevention and so on.
* Added new ways to obtain honor/chaos points upon getting kill-streaks, revenge and internal ranking kills.
#### Misceallaneous Stuff:
* Fixed backend stuff.
  * "Medal of Honor" has been removed and implemented on client UI.
  * Grouped all healing items into a single function with customizable variables.
  * Cleaned and fixed all manufacturing items.
  * Cleaned all character and monster skills.
* Added effect/state handler to allow easier modification of glows or state bonuses.
* Quest System:
  * Added functions to easier create daily and weekly quests by just adding 2 extra variables to the desired quest.
  * Modified some core functions to allow for quests to be timed just by adding the desired time in seconds to the quest.
* Marriage System:
  * Players can get married to one another and obtain a special teleportation skill (can only be used within same GameServer).
  * Can allow players to save a location, this allows players to teleport even while their partner is offline or not in same party.
  * Must place maps within variables to allow players to teleport in that map and also prohibit them.
* Weighted randomness function to handle all the scripts that need to use randomized stuff like items and maps.
  * Can either be completely random or add weight to each item.
#### Chest System:
* Allows system to hand out chests via monster kills (this is not via monster drops).
* The configuration is categorized by map and then by monsters.
  * The chest given and percentage of getting it is configured at the same variable line.
* The given chest can be given on a player-kill or team-kill basis.
* This system allows administrators to hand out any kind of reward.
  * This is mostly intended for those servers that want to hand out low tier mall items.
#### Queue System:
* Independent queue system that can be used for any script.
* Allows or denies, on a per-queue basis, players to join that queue with multiple accounts/characters.
* Needs to be started with a global variable and then can be used throughout the script without having to be recalled each time. Will persist throughout update calls.
#### Unseal System:
* Unseal equipment has been reworked.
  * All of their stats have been modified to be more consistant with their respective class.
* They now consist of a single item, the sealed version is the base equipment and unsealing it just removes an identifier and turns it into unseal version.
* The system also handles different versions of the equipment.
  * Offensive/Defensive/Enhanced/Awakened versions can be added without issues by just adding a few variables in lua. This still uses the same piece of equipment with the same ItemInfo ID.
#### Contract System:
* This system consist of getting contracts by killing monsters throughout the server, upon getting a contract, the monster and quantity needed to kill be randomized. Upon completion of said contract the player will be receive a random reward.
* The system is completely customizable by variables.
  * The monster kill can either update a random contract that requires that monster or all contracts that require that monster.
  * Can be influenced by server drop rate.
  * Can be influenced by player drop rate (fairies and/or amplifiers).
  * The drop rate is on a per-map basis.
    * The level of contract that drops can be also be influenced by different rates.
* The monsters that apply to this system is also modifiable via variables in their corresponding map configuration.
* The rewards are customizable and can be different on a per-map and per-level of contract basis.
#### Level Contest:
* Automated "Level Contest" that rewards a player for reaching the current level limit.
  * This is auto enabled each time the level limit is raised.
* This is automated and keep tracks X amount of players to first reach the level limit.
  * Does not allow players (with multiple account) to get the reward more than once.