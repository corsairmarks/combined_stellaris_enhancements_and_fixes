# Overview

In default (unmodded) Stellaris, when a player conquers a pre-FTL planet (or ringworld segment), he/she is given free districts based on the number of Pops conquered.  The city districts are the wrong type for machine and hive empires, and players receive farming districts on worlds that previously housed a lithoid pre-FTL civilization.  Despite many changes in 3.7 "Canis Minor" for infiltrated and enlightened pre-FTLs, most pre-FTLs still do not receive districts based on what food they consume.  The AI does not receive any bonus districts or buildings except for pre-FTL enlightenment.

It's my opinion that these free districts represent repurposing existing infrastructure for the conqueror's use.  To that end, this mod gives the proper type of city, nexus, or hive districts as appropriate for the conquering empire type.  Second, planets (or ringworld segments) inhabited by lithoid civilizations receive mining districts as opposed to farming districts.  Rogue servitors get organic sanctuaries instead of some of the nexus districts, because preserving some developed areas allows bio-trophies to live in their "natural habitat."  Finally, the AI benefits from these free districts in order to even the playing field.

## A Bit More Detail

This mod started as a response to four very specific, small areas:

1. When conquering pre-FTL planets, human players get free districts to employ about half the population, but the AI does not
2. Machine Empires and Hive Empires are given city districts instead of the appropriate nexus or hive districts
3. When conquering a lithoid pre-FTL planet, the player is given farming districts, which lithoids don't need
4. Necrophage AI players have a special helper event to gain control of pre-FTLs, but it is not actually conquest and thus misses out on some things

To address these issues, this mod re-implements (for both players and AIs) free districts upon acquiring a pre-FTL planet.  The improved "pre-FTL transfer" code generates the appropriate housing/urban districts based on the conquering empire (including some organic sanctuaries for Rogue Servitors).  Mining districts are generated instead of farming districts if the conquered pre-FTL species is lithoid.  The aforementioned pre-FTL transfer is used by the Necrophage AI helper event, pre-FTL infiltration, and any other code that causes a previously-pre-FTL planet to transfer ownership to a space-faring empire.

The districts available on shattered ring world "planets" better match the level of development pre-FTLs can achieve, so pre-FTL ringworlds are now converted to shattered ringworlds upon conquest/infiltration/etc.  Don't forget that the Sanctuary ringworld is stocked with four pre-FTL empires ripe for ~~conquest~~ enlightenment.

# Changes

This mod replaces three events from the base game: `action.14`, `action.140`, and `necroids.6`.  The action events are responsible for the standard military conquest of pre-FTLs and the necroids event is responsible for AI necrophage auto-conquest.  It also replaces the effect responsible for infiltration-related annexation `infiltrate_government_annexation_effect`.

These events and effect are altered to no longer invoke their own code for generating buildings and districts.  Instead custom logic is implemented via the new event `primitive_conquest_enhancements.1` that fires when planet ownership changes from a pre-FTL empire to a space-faring empire, and a series of custom effects.

## Localisation

* English by corsairmarks (author)
* [corsairmarks's Leader Traits MOD Chinese patch](https://steamcommunity.com/sharedfiles/filedetails/?id=2558494770) by Hua Zhang - Chinese localisation

## Compatibility

You do **not** need the Necroids, Lithoids, or First Contact content packs to use this mod.

This mod should be widely compatible with other mods.  Incompatibilities would only occur if other mods also overwrite the same events or effects.  If another mod is attempting to make changes to pre-FTL planet conquest but uses a different method (for example, adding new events activated by on action events such as `on_planet_transfer`, `on_planet_conquer`, or `on_planet_attackers_win`) the end result could be extra districts or other nonsensical behavior after both mods apply their effects.

Built for Stellaris version 3.8 "Gemini."  Not compatible with achievements.  Has built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).

### When to Install

This mod can be safely added or removed from your savegame after the game has started.  It is implemented entirely through events, on actions, and effects.  If you remove it, your game will work normally.

### Known Issues

Overriding an effect or event causes the game to log errors noting the overrides.  Expect to see five lines in the error.log file like these:

```
[00:32:45][game_singleobjectdatabase.h:165]: Object with key: infiltrate_government_annexation_effect already exists, using the one at  file: common/scripted_effects/zz_primitive_conquest_enhancements_first_contact_dlc_scripted_effect_overrides.txt line: 3
[00:32:45][game_singleobjectdatabase.h:165]: Object with key: set_species_graphical_culture already exists, using the one at  file: common/scripted_effects/zz_primitive_conquest_enhancements_pre_ftl_scripted_effects.txt line: 2
[00:32:51][eventmanager.cpp:369]: an event with id [necroids.6] already exists!  file: events/necroids_events_1.txt line: 592
[00:32:51][eventmanager.cpp:369]: an event with id [action.14] already exists!  file: events/on_action_events_1.txt line: 3720
[00:32:51][eventmanager.cpp:369]: an event with id [action.140] already exists!  file: events/on_action_events_1.txt line: 3786
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add machine/hive empire support
* 1.2.0 Ringworld support (e.g. Sanctuary), add images and explanations
* 1.2.1 Mark as compatible with Stellaris version 3.0 "Dick" - no script changes
* 1.2.2 Remove extra images files to keep distribution lightweight (no script changes)
* 1.3.0 Add handling for primitive infiltration
    * Free buildings and districts processing is more intelligent
    * Changed "generate districts/buildings" to a pair of custom on_actions
* 2.0.0 Update for compatibility with Stellaris version 3.1 "Lem"
    * Update to use new arithmetic syntax
    * Update minor underlying game changes (mainly to support new features in the base game)
* 2.1.0 Improve mod reliability and safety
    * Ensure AI Necrophage homeworlds cannot be fully depopulated by their special primitive conquest event (unlikely to occur but better to be safe)
    * Do not attempt to auto-resettle Necrophage Pops to a world they can't live on (modified for regular land appropriation in 3.1 but not the AI Necrophage helper event)
    * Add trigger to account for a primitive planet's primitive age OR its Pop count when adding free buildings/districts - whichever value is "higher" is used to determine how much to build
* 3.0.0 Update for compatibility with Stellaris version 3.2 "Lem"
    * More intelligent districts based on a planet's district set
    * Angler on oceans get uncapped farming districts
    * Add handling for primitive enlightenment
    * Ringworld setup is even more intelligent
    * Built-in colossus weapons that allow the "conquest" of primitive worlds (Deluge Machine, Nanobot Diffuser) now also get infrastructure
    * My custom colossus weapon (Necrophagic Spore Diffuser) now also gets infrastructure
* 4.0.0 Update for Stellaris version 3.3 "Libra" - integrate new triggers from the base game
* 4.1.0 More updates for 3.3 "Libra" and ringworld primitives have their homeworld transformed into a shattered ringworld segment
    * Reanimators get a Dread Encampment instead of a Research Lab
    * Fix primitive unity building (wrongly spawned an Autochthon Monument) - usually only Early Space Age primitives would have a unity building
    * Previous ringworld conquest conversion still exists for non-standard-sized ringworlds (not size 10)
    * Finally update the example screenshots
* 5.0.0 Update for Stellaris version 3.4 "Cepheus" - integrate base game changes
* 5.1.0 Minor trigger and effect enhancements
* 6.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Update overridden events with underlying game changes
    * Use built-in on-action `on_planet_transfer` now that it provides the previous owner as `fromfrom`
    * Remove custom on_actions `on_primitive_planet_transferring` and `on_primitive_planet_transferred`
* 6.0.1 Ensure that free buildings are added correctly for primitive conquest - due to underlying Stellaris changes, the conquest event now fires _before_ the primitive buildings are removed, so they must be manually cleared
* 6.1.0 Bugfix and compatibility trigger
    * Undo changes to unity buildings spawned after a primitive conquest - Uplink Nodes and Synapse Nodes are correct
    * Add a compatibility trigger for other mods to check whether this one is active
* 7.0.0 Update for Stellaris version 3.7 "Canis Minor"
    * Remove obsolete event overrides
    * Add new effect overrides for infiltration annexation and empire match-graphical-culture-to-main-species
    * Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)
* 7.0.1 Improve support for Planetary Diversity - notably for starts on Techno-Organic planets
* 7.1.0 Mark as compatible with Stellaris 3.8 version "Gemini" - no script changes

## Source Code

Hosted on [Github](https://github.com/corsairmarks/primitive_conquest_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.