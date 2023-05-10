# Overview

Do you wish your empire's maze of incomprehensible bureaucracy provided more benefits?  Do your people feel a sense of national pride when queueing to file their forms in quadruplicate hard-copy?  Is technically correct the best kind of correct?  Then this mod is for you!

# Changes

Civic: Bureaucracy offers a fairly mild benefit by default: +1 unity and +1 stability per Bureaucrat.  With this mod, Bureaucrats also provided +2 amenities, which officially "represent planetary infrastructure and jobs dedicated towards fulfilling the day-to-day needs of the population" provided by the massive administrative apparatus present in Byzantine Bureaucracies. And what sort of paperwork hellscape would be complete without another, higher rank of functionary? Enter the Magistrate ruler-stratum job.

Magistrates provide unity, stability, and amenities (although more than rank-and-file Bureaucrats) and additionally reduce crime by -10.  The need for Magistrates is highest at the administrative centers for their empire - they independently form Seats of the Magistracy at the imperial capital and sector capitals.  Should the imperial or a sector capital be relocated, the Magistrates move with the capital.  Fully-upgraded Administrative Complexes and Administrative Arcologies also offer a Magistrate job to oversee the rest of the Bureaucrats.

## Compatibility

This mod overwrites the `bureaucrat` job in order to add amenities to their output under Civic: Byzantine Bureaucracy. The Administrative Complex building (`building_bureaucratic_3`) and Administrative Arcology district (`district_arcology_administrative`) are also overridden to add the new Magistrate job for empires with Civic: Byzantine Bureaucracy.  All other functionality is implemented through custom events and new game objects (a job and deposit).  This mod has built-in compatibility with [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835) - this mod must load **before** Planetary Diversity.

Built for Stellaris version 3.8 "Gemini."  Not compatible with achievements.

### When to Install

This mod can be safely added after the game has started.  Although this mod does add two game objects, Stellaris is fairly forgiving in ignoring unknown jobs and deposits if it is removed from an ongoing game.  Back up your savegame before trying to remove a mod, even this one.

### Recommended Companion Mods

* [Civic: Organic Zealots](https://steamcommunity.com/sharedfiles/filedetails/?id=2920668465) adds a brand-new civic - play as a homicidal empire determined to eliminate artificial intelligence
* [Civic: Philosopher King - Enhanced](https://steamcommunity.com/sharedfiles/filedetails/?id=2774084358) lightly enhances Civic: Philosopher King to grant bonus levels to civilian leaders (similar to the bonus levels for military leaders from Civic: Distinguished Admiralty)
* [Origin: Jovian League](https://steamcommunity.com/sharedfiles/filedetails/?id=2682659676) adds a brand-new origin that allows almost any empire to begin spanning four small colonies on the moons of a gas giant rather than they typical large, single planet
* [Corsair's Custom Empires: Eldanær Stellar Authority](https://steamcommunity.com/sharedfiles/filedetails/?id=2496360535) adds a prescripted empire with a narrative backstory which happens to use Civic: Byzantine Bureaucracy; also features a new colossus weapon for fungoid necrophage empires

## Known Issues

Overriding buildings and jobs causes the game to log errors noting the overrides.  Expect to see four lines in the error.log file like these:

```
[01:50:22][game_singleobjectdatabase.h:165]: Object with key: district_arcology_administrative already exists, using the one at  file: common/districts/11_civic_byzantine_bureaucracy_enhanced_arcology_districts.txt line: 2
[01:50:22][game_singleobjectdatabase.h:165]: Object with key: building_bureaucratic_3 already exists, using the one at  file: common/buildings/18_civic_byzantine_bureaucracy_enhanced_unity_building_overrides.txt line: 2
[01:50:22][game_singleobjectdatabase.h:165]: Object with key: building_league_offices already exists, using the one at  file: common/buildings/18_civic_byzantine_bureaucracy_enhanced_unity_building_overrides.txt line: 137
[01:50:24][game_singleobjectdatabase.h:165]: Object with key: bureaucrat already exists, using the one at  file: common/pop_jobs/12_civic_byzantine_bureaucracy_enhanced_specialist_job_overrides.txt line: 2
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)
* 2.0.0 Update for Stellaris version 3.7 "Canis Minor"
    * Add an override of a new archaeotech building related to bureaucrats to also give +1 magistrates
    * Update magistrates to be affected by the same archaeotech building
    * Integrate underlying game changes
* 2.0.1 Fix spacing in description for Civic: Byzantine Bureaucracy
* 2.0.2 Improve support with Planetary Diversity `bureaucrat` job override
* 2.1.0 Update for Stellaris version 3.8 "Gemini" - integrate underlying game changes

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/civic_byzantine_bureaucracy_enhanced)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.