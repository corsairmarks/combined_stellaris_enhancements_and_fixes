# Overview

In default (unmodded) Stellaris, when a player conquers a primitive planet (or ringworld segment), he/she is given free districts based on the number of Pops conquered.  The city districts are the wrong type for machine and hive empires, and players receive farming districts on worlds that previously housed a lithoid primitive civilization.  Despite some changes in 3.2 "Herbert" for enlightened primitives, most primitives still do not receive districts based on what food they consume.  The AI does not receive any bonus districts or buildings except for primitive enlightenment.

It's my opinion that these free districts represent repurposing existing infrastructure for the conqueror's use.  To that end, this mod gives the proper type of city, nexus, or hive districts as appropriate for the conquering empire type.  Second, planets (or ringworld segments) inhabited by lithoid civilizations receive mining districts (or extra ringworld housing) as opposed to farming districts/segments.  Rogue servitors get organic sanctuaries instead of some of the nexus districts, because preserving some developed areas allows bio-trophies to live in their "natural habitat."  Finally, the AI benefits from these free districts in order to even the playing field.

## A Bit More Detail

This mod started as a response to four very specific, small areas:

1. When conquering primitive planets, human players get free districts to employ about half the population, but the AI does not
2. Machine Empires and Hive Empires were given city districts instead of the appropriate nexus or hive districts
3. When conquering a lithoid primitive planet, the player is given farming districts, which lithoids wouldn't need
4. Necrophage AI players have a special helper event to gain control of primitives, but it is not actually conquest and thus misses out on some things

To address these issues, this mod implements free districts upon conquering a primitive planet for both players and AIs.  It also generates the appropriate housing/urban districts based on the conquering empire (including some organic sanctuaries for Rogue Servitors).  Mining districts are generated instead of farming districts if the conquered primitive species is lithoid.  Finally, it triggers the aforementioned free district creation in the Necrophage AI helper event, primitive infiltration, and primitive enlightenment (including advancing on their own).  In combination, these changes should help AI players be a bit more successful when acquiring primitive planets.

## Primitive Enlightenment Now Included

The "Technological Enlightenment" observation station mission was still another place where the game did something different when converting primitives for use by a regular empire. A fixed amount of districts and buildings (including a branch office building, which was probably intended to be Commercial Zones instead) were generated.  Although it accounted for ringworlds (and as of 3.2 lithoids), it was still significantly different from other primitive conversions.

This mod continues its trend of unification by hooking up the enlightenment finisher event to the same district-generation code as primitive conquest.  This event also controls the planet infrastructure self-enlightened primitives receive.  Additionally, I further adjusted the shared district/building generation to be even smarter for ringworlds!

# Changes

This mod replaces six events from the base game: `action.14`, `action.140`, `necroids.6`, `observation.3009`, `primitive.16`, and `primitive.17`.  The action events are responsible for the standard military conquest of primitives, the necroids event is responsible for necrophage auto-conquest, the observation event is responsible for primitive infiltration, and the primitive events are related to technological enlightenment.  These events are now altered to invoke the same code for generating buildings and districts.

Most of the new custom logic is implemented outside of these events.  Version 1.3.0 of this mod added two custom on_actions: `on_primitive_planet_transferring` that fires before planet ownership changes and `on_primitive_planet_transferred` that fires after planet ownership changes.  District/building generation is triggered by `on_primitive_planet_transferred`.  The most useful part of all of this is that you can make other mods tie in to these on_actions to create new effects when primitives are conquered/infiltrated.

## Localisation

* English by corsairmarks (author)
* [corsairmarks's Leader Traits MOD Chinese patch](https://steamcommunity.com/sharedfiles/filedetails/?id=2558494770) by Hua Zhang - Chinese localisation

## Known Issues

Due to how events are loaded by Stellaris, the file from this mod is named to load before the base game files.  Events with duplicate IDs generate entries in the error.log file (and the first one loaded is used), so this mod is expected to generate six error lines that look similar to this:

```
[01:33:07][eventmanager.cpp:355]: an event with id [necroids.6] already exists!  file: events/necroids_events_1.txt line: 548
[01:33:07][eventmanager.cpp:355]: an event with id [observation.3009] already exists!  file: events/observation_events.txt line: 4480
[01:33:07][eventmanager.cpp:355]: an event with id [action.14] already exists!  file: events/on_action_events_1.txt line: 5824
[01:33:07][eventmanager.cpp:355]: an event with id [action.140] already exists!  file: events/on_action_events_1.txt line: 5890
[01:33:07][eventmanager.cpp:355]: an event with id [primitive.16] already exists!  file: events/primitive_events.txt line: 304
[01:33:07][eventmanager.cpp:355]: an event with id [primitive.17] already exists!  file: events/primitive_events.txt line: 629
```

## Compatibility

You do **not** need the Necroids or Lithoids content packs to use this mod.

This mod should be widely compatible with other mods.  Incompatibilities would only occur if other mods also overwrite the same event IDs.  If another mod is attempting to make changes to primitive planet conquest but uses a different method (for example, adding new events activated by on action events such as `on_planet_transfer`, `on_planet_conquer`, or `on_planet_attackers_win`) the end result could be extra districts or other nonsensical behavior after both mods apply their effects.

Built for Stellaris version 3.2.\* "Herbert."  Not compatible with achievements.

### When to Install

This mod can be safely added or removed from your savegame after the game has started.  It is implemented entirely through custom events, on actions, and effects.  If you remove it, your game will work normally.

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add machine/hive empire support
* 1.2.0 Ringworld support (e.g. Sanctuary), add images and explanations
* 1.2.1 Flagged as compatible with Stellaris 3.0 "Dick" (no script changes)
* 1.2.2 Remove extra images files to keep distribution lightweight (no script changes)
* 1.3.0 Add handling for primitive infiltration
    * Free buildings and districts processing is more intelligent
    * Changed "generate districts/buildings" to a pair of custom on_actions
* 2.0.0 Update for compatibility with Stellaris 3.1 "Lem"
    * Update to use new arithmetic syntax
    * Update minor underlying game changes (mainly to support new features in the base game)
* 2.1.0 Improve mod reliability and safety
    * Ensure AI Necrophage homeworlds cannot be fully depopulated by their special primitive conquest event (unlikely to occur but better to be safe)
    * Do not attempt to auto-resettle Necrophage Pops to a world they can't live on (modified for regular land appropriation in 3.1 but not the AI Necrophage helper event)
    * Add trigger to account for a primitive planet's primitive age OR its Pop count when adding free buildings/districts - whichever value is "higher" is used to determine how much to build
* 3.0.0 Update for compatibility with Stellaris 3.2 "Lem"
    * More intelligent districts based on a planet's district set
    * Angler on oceans get uncapped farming districts
    * Add handling for primitive enlightenment
    * Ringworld setup is even more intelligent

## Source Code

Hosted on [Github](https://github.com/corsairmarks/primitive_conquest_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.