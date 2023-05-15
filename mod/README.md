# Overview

Have you ever wanted to entrust your Battle Thralls to lead on the battlefield? With this mod you now have the option to allow your Battle Thralls greater freedom to command ships and armies as Admirals and Generals.  Or maybe some organic insight is just what your Rogue Servitors need to build a better paradise?  This mod also allows you to designate Bio-Trophy species as Organic Advisors as Governors and Scientists.  Should you need to wield the "chaotic and violent organic nature" you also have the option to grant your Organic Advisors the Full Military Service species right so they can serve as Admirals and Generals - but not armies.  Even the most jaded Rogue Servitors would never send a mass of the precious Bio-Trophies into battle!

In addition to Battle Thralls being eligible to be rolled as military leaders and Bio-Trophies as non-ruler leaders, any species with Full Military Service can be rewarded as a promoted captain after destroying an enemy fleet.  The free admiral from a promotion is built-in, but by default it only ever rewards admirals of the owner's main species.

# Changes

The Battle Thralls slavery type is allowed to be assigned the Full Military Service service type, which then allows them to become military leaders - Admirals and Generals.  In order to achieve this, I've attached an event to `on_leader_spawned` that can alter the species of the spawned leader to any species which has Full Military Service; this applies anywhere leaders are created.  The leader's species is randomly rerolled by selecting a Pop out of all those that have Full Military service and using that Pop's species, and is thus implicitly weighted based on the relative population size of the eligible species.  Second, I've updated Full Military Service to be selectable for Battle Thralls.  As a bonus for allowing Battle Thralls even greater responsibility, their Pops are 10% happier when given Full Military Service.

In addition to allowing Battle Thralls to have Full Military Service, I slightly updated the conditions for which it is allowed.  Necrophages now cannot set any species that is not their main necrophage species to have Full Military Service (as described in the origin) and the allowing Full Military Service for robots now requires Synthetic Personality Matrix rather than Droids.  Syncretic Proles (as described by the trait) and non-sentients cannot be military leaders.

Because this mod was inspired by my role-play for the [Eldanær Stellar Authority](https://steamcommunity.com/sharedfiles/filedetails/?id=2496360535) it also allows bypassing the xenophobic and necrophage restrictions for allowing Full Military Service to Battle Thralls.  You can bypass the restrictions by using the custom edict "Decree: Honored Protectors" which will let you declare a species of Battle Thralls as "Honored Protectors" for 100 unity.  Honored Protectors are automatically set to Full Military Service, but may later be demoted.

Bio-Trophies seemed like another candidate for being leaders under special conditions.  Building on the framework for "Decree: Honored Protectors," it is now possible for Rogue Servitors to designate one or more species of Bio-Trophies as as advisors.  They may use the custom edict "Decree: Organic Advisors" to declare a species of Bio-Tropies as "Organic Advisors" for 100 unity.  Organic Advisors can produce civilian leaders by default, and may produce military leaders if set to Full Military Service.

Finally, as a minor quality-of-life enhancement, I have also attached an event to `on_fleet_destroyed_perp` that will fire after `leader.1` (captain promoted to admiral) has generated a leader of the owner's main species.  This allows the species of that leader to be rerolled if the empire in question allows Full Military Service for any non-main species - including Battle Thralls and Bio-Trophies.

## Localisation

This mod is somewhat localized for every language supported by Stellaris - mainly because it reuses the built-in localisation.

However, the new edicts to declare Battle Thralls as Honored Protectors or Bio-Trophies as Organic Advisors are not localised - that is because it is my original writing.  The English text is used as a placeholder for other languages.  If you want to translate it into your language, please leave a comment or message me.

## Compatibility

Because this mod replaces several built-in objects, it is inherently incompatible with mods that alter the same objects.  While I doubt most mods will fiddle with the `can_be_military_leader` trigger it is likely any mods that are altering citizenship, military service, and/or slavery type could overlap with this one.  The only species rights this mod overrides are `military_service_full` and `military_service_limited`.  To support Bio-Trophies as leaders, this mod also overrides four game rules: `can_generate_army_from_species`, `can_generate_leader_from_species`, `can_generate_leader_from_pop`, and `can_generate_military_leader_from_pop`.

This mod is specifically engineered to be compatible with my other mod that affects military service: [Deassimiliate Machines](https://steamcommunity.com/sharedfiles/filedetails/?id=2553812372).

Built for Stellaris version 3.8 "Gemini."  This mod is not compatible with achievements.

### When to Install

This mod can be safely added to your savegame after the game has started, but not removed.  Because this mod alters the game rules, removing it could result in problems as the game detects a now-invalid citizenship/military service combination - or it might just force your Battle Thralls out of military full service.  If you'd like to find out, make a backup of your savegame before experimenting.

### Recommended Companion Mods

If you like species traits that add leader traits, check out my mod [Leader Traits: All Eligible Species Traits](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295).  It is fully compatible with this mod.  The most notable interaction occurs when your Battle Thrall species is chosen for becoming a random admiral after destroying an enemy fleet - with this mod your promoted captains will properly gain their species traits.

## Known Issues

This mod overrides a built-in trigger `can_be_military_leader` and a species rights `military_service_full` and `military_service_limited`.  These overrides each cause the game to log an error, so expect to see three lines in error.log like this:

```
[00:47:01][game_singleobjectdatabase.h:165]: Object with key: can_be_military_leader already exists, using the one at  file: common/scripted_triggers/01_battle_thrall_military_leaders_scripted_trigger_overrides.txt line: 4
[00:47:01][game_singleobjectdatabase.h:165]: Object with key: military_service_full already exists, using the one at  file: common/species_rights/military_service_types/20_battle_thrall_special_military_service.txt line: 9
[00:47:01][game_singleobjectdatabase.h:165]: Object with key: military_service_limited already exists, using the one at  file: common/species_rights/military_service_types/20_battle_thrall_special_military_service.txt line: 170
```

## Change Log

* 1.0.0 Initial version
* 1.1.0 Add event to flag mod as installed
* 1.1.1 Remove extra images files to keep distribution lightweight (no script changes)
* 1.2.0 remove monthly pulse for mod flag
* 1.3.0 Enhance compatibility with [Gender Nonbinary Leaders](https://steamcommunity.com/sharedfiles/filedetails/?id=2528614880)
* 1.4.0 Enhance compatibility with my other mods that work with changing leader species - no gameplay changes in this mod
* 1.5.0 Add edict "Decree: Honored Protectors" so players can choose Battle Thralls they'd like to allow Full Military Service, despite being xenophobic and/or a necrophage
* 1.5.1 Add test event, prevent Fanatic Purifiers from naming Honored Protectors
* 1.6.0 Update for compatibility with Stellaris version 3.1 "Lem"
    * No homicidal empires can use the edict (just in case)
* 2.0.0 Upgrade for compatibility with Stellaris version 3.2 "Herbert"
    * Battle Thrall leaders will match the gender of their new species
    * Leader reselected to be a Battle Thrall species which were originally from gendered (binary, male-exclusive, or female-exclusive) species must be cloned to have their gender set to `indeterminable` and vice versa - this is disabled when combined with "Gender Nonbinary Leaders" because that mod does its own cloning shenanigans
    * Integrates with Retain Leaders from Integrated Subjects to avoid duplicate cloning
* 2.1.0 Enable special leadership decree for Rogue Servitors to have Organic Advisors
    * Rename mod to "Special Leadership Privileges for Battle Thralls & Bio-Trophies"
    * Add edict "Decree: Organic Advisors" so players can choose Bio-Trophies as civilian leaders (optionally also military leaders), despite being Rogue Servitors
    * Edit game rules to allow Bio-Trophies to be civilian leaders (with decree) and eligible to be military leaders (but not armies) if optionally granted Full Military Service
    * Fix a bug where you couldn't re-open the Honored Protectors edict
* 2.1.1 Fix incorrect filename
* 3.0.0 Update for Stellaris version 3.3 "Libra"
    * Update Decrees to cost unity instead of influence
    * Integrate underlying game change - zombies cannot produce leaders
* 4.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Integrate underlying game change - SALVAGER and SHROUDWALKER species classes do not use gender
    * Reduce duplicated AI-weight code for Honored Protectors and Organic Advisors
* 4.1.0 Minor trigger enhancement
* 5.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Update overridden game rules with underlying game changes
    * Update `species_rights` to override files based on changed directories in the base game
    * Refactor events to use inline script in order to reduce code duplication (no change to functionality)
* 6.0.0 Enhance military leadership and service overrides and compatibility triggers
    * Add override of `military_service_limited` to allow main species that are _not_ smart enough for leadership
    * Add override of `can_generate_military_leader_from_pop` to ensure only species who are smart enough for leadership
    * Add a compatibility trigger for other mods to check whether this one is active
    * Consume the compatibility trigger from another mod
    * Remove old compatibility global flag
* 6.0.1 Add some missing compatibility triggers, fix using a trigger in the wrong scope in `can_generate_leader_from_species`
* 6.0.2 Fix a scope error in `military_service_full`
* 6.1.0 Mark as compatible with Stellaris version 3.7 "Canis Minor" - no script changes
* 7.0.0 Update for Stellaris version 3.8 "Gemini"
    * Any necrophage species may become leaders in a necrophage empire
    * Simplify gender-matching for leaders whose species has changed

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/battle_thrall_military_leaders)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.
