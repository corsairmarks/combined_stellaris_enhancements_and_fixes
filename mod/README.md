# Overview

Feeling un-energized by Betharian Power Plants? Then this mod is for you! Betharian Power Plants provide a hefty boost to Technician base energy output and add extra generator district slots to the planet. Now that Betharian Stone can be put to good use powering your empire's progress!

Requested by [Peter34](https://steamcommunity.com/profiles/76561198035019113).

# Changes

Betharian Power Plants boost Technician output by base energy output by +2 and provide +4 generator district slots to the planet.

## Compatibility

As the title suggests, this mod overwrites the entry for the Betharian Power Plant (`building_betharian_power_plant`). Also overridden is the Betharian Fields deposit `d_betharian_deposit` - it is now slightly more likely to occur on dry planets.

Built for Stellaris version 3.7 "Canis Minor."  Not compatible with achievements.

### When to Install

This mod can be safely added or removed after the game has started. It only replaces default game objects, but may cause unemployment or negative generator districts when removed.  Back up your savegame before trying to remove a mod, even this one.

## Known Issues

Overriding a building or deposit causes the game to log errors noting the overrides.  Expect to see two lines in the error.log file like these:

```
[15:16:48][game_singleobjectdatabase.h:165]: Object with key: building_betharian_power_plant already exists, using the one at  file: common/buildings/20_building_deposit_enhancements_deposit_building_overrides.txt line: 5
[15:16:56][game_singleobjectdatabase.h:165]: Object with key: d_betharian_deposit already exists, using the one at  file: common/deposits/11_building_deposit_enhancements_planetary_deposit_overrides.txt line: 8
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)
* 2.0.0 Update for Stellaris version 3.7 "Canis Minor"
    * Remove alterations for Xeno Zoo
    * Remove no-longer-necessary economic category `planet_culture_workers` override

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/building_deposit_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.