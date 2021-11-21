# Overview

Are you frustrated that you have a limited supply of Titanic Beasts or Imperial Legions or Azizian Armies?  Well fret no more!  This mod actively tracks how many many of each type you own and lets you build reinforcements up to the regular cap for each type.

Additionally, this mod now entitles you to number of Titanic Beasts equal to your successful Titanic Life projects times three (instead of three no matter how many times you have completed the project).  Have 2 Titanic Life worlds?  Now your maximum is 6 instead of 3.

To make things easier, this mod recalculates army counts and the maximum Titanic Beasts for any qualifying countries when you load your savegame - in particular this means it will immediately apply to your existing, single-player games without any hassle.  It also recalculates monthly because some things that might alter the amount of armies aren't able to be tracked directly.  If recalculation is needed manually, run `event limited_army_counter_fix.3` from the console.

# Changes

The counter-limited army types (Titanic Beasts, Azizian Armies, and Imperial Legions) now allow you to build replacements when killed, up to the original caps: 3 for Azizians, 12 for Imperial Legions, and 3 Titanic Beasts per world with a successful Titanic Life research project).

This mod won't affect any other kinds of armies.

## Compatibility

Built for Stellaris version 3.2.\* "Herbert."  Not compatible with achievements.

Overwrites the three built-in counter-limited armies in order to improve their counter usage: `titanic_assault_army`, `titanic_azizian_assault_army`, and `imperial_legion`.  The `titanic_assault_army` also has its maximum counter scaled by the number of owned planets where the Titanic Life study was successfully completed.

Preempts the event `colony_mod.101` (the positive Titanic Life outcome) in order to implement the scaling maximum and event `emperor.450` to remove its effects.  Counter-limited army decrementing is now handled in `limited_army_counter_fix.1` for all three types.

This mod is incompatible with other mods that also replace the same army types or make changes to the same events.

### When to Install

This mod can be safely added to your savegame after the game has started.  If removed, your game should generally function normally - Stellaris is usually fairly forgiving and just ignores missing events that were attached to an `on_action`.  Because this mod uses the same counter variables as the default code, the built-in army limits will be enforced.  Always back up your savegame before trying to remove a mod.

## Known Issues

Because this mod replaces three army types (`titanic_assault_army`, `titanic_azizian_assault_army`, and `imperial_legion`) and preempts two events (`colony_mod.101` and `emperor.450`), it is expected to generate five lines in error.log like this:

```
[12:35:16][game_singleobjectdatabase.h:147]: Object with key: titanic_assault_army already exists
[12:35:16][game_singleobjectdatabase.h:147]: Object with key: titanic_azizian_assault_army already exists
[12:35:16][game_singleobjectdatabase.h:147]: Object with key: imperial_legion already exists
[12:35:18][eventmanager.cpp:355]: an event with id [colony_mod.101] already exists!  file: events/colony_events_3.txt line: 234
[12:35:18][eventmanager.cpp:355]: an event with id [emperor.450] already exists!  file: events/nemesis_emperor_events.txt line: 2304
```

When an empire loses a Titanic Life planet (thus lowering their cap) while recruiting Titanic Beasts on another planet and would exceed the new, lower cap, ideally army recruitment would be be cancelled.  Armies cannot be dequeued via script, so instead this mod watches when armies are recruited and automatically deletes and refunds armies that would be over the cap.  Because of a possible crash, the army deletion occurs one day after the "over cap" army finishes being recruited.

## Changelog

* 1.0.0 Initial version
* 1.0.1 Fix thumbnail
* 2.0.0 Mark as compatible with Stellaris 3.1 "Lem" - update to use new arithmetic syntax
* 2.1.0 Mark as compatible with Stellaris 3.2 "Herbert" - no script changes

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/limited_army_counter_fix)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.