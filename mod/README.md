# Overview

Wish that your empire's Ruler jobs were a little bit more varied than just endless Politicians?  Then this mod is for you!

Similar to how the Merchant Guilds, Exalted Priesthood, Aristocratic Elite, and Technocracy civics swap some Politician jobs out for their relevant jobs, capital buildings for regular, **non\-**MegaCorp empires will now _also_ swap out some Politician jobs based on the planet's colony designation:

* Trade-related colonies will swap for Merchants
* Unity-related colonies will swap for High Priests (spiritualist empires) or Nobles (Aristocratic Elite, imperial authorities, or the Galactic Emperor)
* Research-related colonies will swap for Science Directors

These swaps combine with those for the leader-swap civics, so that some planets may end up with no Politicians at all.

# Changes

Replaces five of the built-in capital buildings: `building_capital`, `building_major_capital`, `building_system_capital` (regular empire capital upgrades), `building_hab_major_capital` (the habitat capital upgrade - shared amongst all empire types), and `building_imperial_capital` (the Galactic Imperium capital buildings for regular empires).

Although only loosely-related to this mod's main purpose, it also adds an event so that Aristocratic Elite empires begin with a Noble Estates building, as long as it does not already have one and there is room to add a building.

## Compatibility

Compatible with any mod that does not overwrite the same buildings.  For mods that overwrite all the capital buildings, this mod's buildings will likely take precedence.  Might have problems with other mods that remove the expected colony types, but I highly doubt any mods do that.

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

### Recommended Companion Mods

* [Enhanced Trade Districts and Designations](https://steamcommunity.com/sharedfiles/filedetails/?id=2641081470) enhances the built-in trade-related districts to provide extra Merchant and Clerk jobs based on civics, traditions, and colony designations
* [More Standard Districts](https://steamcommunity.com/sharedfiles/filedetails/?id=2650611194) adds more district types to planets and habitats based on the types of districts available for other types of planets: Unity-generation, Military, Research, and Commercial

### When to Install

This mod can be safely added to your savegame after the game has started.  If you remove it, your game should function normally, although you will likely have Ruler Pops become unemployed as capital building jobs shift back to normal Politician jobs.  Always back up your savegame before trying to remove a mod.

## Known Issues

This mod overwrites five buildings, so expect to see five errors in your error.log similar to these:

```
[15:08:43][game_singleobjectdatabase.h:165]: Object with key: building_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 10
[15:08:43][game_singleobjectdatabase.h:165]: Object with key: building_major_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 304
[15:08:43][game_singleobjectdatabase.h:165]: Object with key: building_system_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 623
[15:08:43][game_singleobjectdatabase.h:165]: Object with key: building_hab_major_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 958
[15:08:43][game_singleobjectdatabase.h:165]: Object with key: building_imperial_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1474
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Aristocratic Elite gains Noble Estates on their homeworld, as long as it does not already have one and there is room to add a building
    * Bugfix: refer to the right civic for Aristocratic Elite job swaps
* 1.1.1 Fix bug when checking if a country is the Galactic Emperor
* 2.0.0 Update for Stellaris version 3.4.2 "Cepheus"
    * Use memory optimization feature for triggers
    * Update habitat capital building with deficit changes
* 2.1.0 Update for Stellaris version 3.4.3 "Cepheus" - apply underlying fix for duplicate alloy deficit penalty (remove it from the habitat capital building)
* 2.2.0 Add a dummy colony designations (from other supported mods) to stop spamming the error log when they are not installed
* 3.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Integrate the Origin: Knights of the Toxic God changes
    * Integrate the new tradition-based changes and federation bonus culture workers (including adding the culture workers to the imperial capitol - appears to be an oversight by PDS)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/building_capital_colony_type_job_swaps)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.