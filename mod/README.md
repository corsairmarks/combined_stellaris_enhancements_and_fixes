# Overview

Feeling un-energized by Betharian Power Plants? Or un-entertained by Alien Zoos? Then this mod is for you! Betharian Power Plants provide a hefty boost to Technician base energy output and add extra generator district slots to the planet. Now that Betharian Stone can be put to good use powering your empire's progress! Alien Zoos have once again found space for a Culture Worker job, as well as an additional Culture Worker per 25 Pops. On top of that, the Zoo boosts Culture Worker output by 15%. Celebrate the supremacy of your empire's culture and achievement in gathering specimens from across the galaxy!

Requested by [Peter34](https://steamcommunity.com/profiles/76561198035019113).

# Changes

Betharian Power Plants boost Technician output by base energy output by +2 and provide +4 generator district slots to the planet. Alien Zoos provide +2 Entertainer jobs and +1 Culture Worker job, as +1 additional Culture Worker job per 25 Pops, and +15% Culture Worker output.

## Compatibility

As the title suggests, this mod overwrites the entries for the Betharian Power Plant and Alien Zoo (`building_betharian_power_plant` and `building_xeno_zoo`). In order to be able to grant Culture Workers a specific bonus, it was necessary to override their economic category `planet_culture_workers`. Also overridden is the Betharian Fields deposit `d_betharian_deposit` - it is now slightly more likely to occur on dry planets.

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

### When to Install

This mod can be safely added or removed after the game has started. It only replaces default game objects, but may cause unemployment or negative generator districts when removed.  Back up your savegame before trying to remove a mod, even this one.

## Known Issues

Overriding a building, deposit, or economic category causes the game to log errors noting the overrides.  Expect to see four lines in the error.log file like these:

```
[15:16:45][game_singleobjectdatabase.h:165]: Object with key: planet_culture_workers already exists, using the one at  file: common/economic_categories/10_building_deposit_enhancements_economic_category_overrides.txt line: 1
[15:16:48][game_singleobjectdatabase.h:165]: Object with key: building_betharian_power_plant already exists, using the one at  file: common/buildings/20_building_deposit_enhancements_deposit_building_overrides.txt line: 5
[15:16:48][game_singleobjectdatabase.h:165]: Object with key: building_xeno_zoo already exists, using the one at  file: common/buildings/20_building_deposit_enhancements_deposit_building_overrides.txt line: 95
[15:16:56][game_singleobjectdatabase.h:165]: Object with key: d_betharian_deposit already exists, using the one at  file: common/deposits/11_building_deposit_enhancements_planetary_deposit_overrides.txt line: 8
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/building_deposit_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.