# Overview

Celebrate your empire's culture again by constructing Leisure Districts on habitats and Leisure Arcologies on ecumenopoleis! Habitat Leisure Districts once again provide 2 Entertainer jobs and a Culture Worker job and ecumenopolis Leisure Arcologies once again provide 3 Entertainer jobs and 3 Culture Worker jobs. With the introduction of ethic-specific Culture Worker bonuses in Stellaris version 3.5 "Fornax," the job again has a unique identity beyond "society researcher."

# Changes

Leisure Districts on habitats again provide +2 Entertainer jobs and +1 Culture Worker job and Leisure Arcologies on ecumenopoleis provide +3 Entertainer jobs and +3 Culture Worker jobs.

## Compatibility

The Leisure District `district_hab_cultural` and the Leisure Arcology `district_arcology_leisure` are overridden in order to reintroduce Culture Workers.  This mod has built-in compatibility with [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).

Built for Stellaris version 3.7 "Canis Minor."  Not compatible with achievements.

### When to Install

This mod can be safely added or removed after the game has started. It only replaces default game objects, but may cause unemployment when removed.  Back up your savegame before trying to remove a mod, even this one.

### Recommended Companion Mods

* [Buildings: Betharian Power Plant and Alien Zoo - Enhanced](https://steamcommunity.com/sharedfiles/filedetails/?id=2916269980) adds Culture Workers back to the Alien Zoo - for people of culture, like you!
* [More Standard Districts](https://steamcommunity.com/sharedfiles/filedetails/?id=2650611194) recognizes when this mod is active and also adjusts its planetary Leisure Districts to support 1 Entertainer job and 1 Culture Worker job

## Known Issues

Overriding a district causes the game to log errors noting the overrides.  Expect to see two lines in the error.log file like these:

```
[01:13:24][game_singleobjectdatabase.h:165]: Object with key: district_arcology_leisure already exists, using the one at  file: common/districts/11_district_leisure_cultural_arcology_district_overrides.txt line: 1
[01:13:24][game_singleobjectdatabase.h:165]: Object with key: district_hab_cultural already exists, using the one at  file: common/districts/13_district_leisure_cultural_habitat_district_overrides.txt line: 5
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)
* 1.2.0 Mark as compatible with Stellaris version 3.7 "Canis Minor" - no script changes

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/district_leisure_cultural)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.