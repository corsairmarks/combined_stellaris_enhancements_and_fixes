# Overview

Do you wish your Trade Stations and Commercial Ring Worlds had a little more "oomph?"  Or maybe you're disappointed with how far ahead Ecumenopolis Commercial Worlds got with my mod [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991).  Then this mod is for you!  The Trade Station and Commercial Ring World colony designations now also boost the build-speed of commercial buildings and the relevant commercial districts by 25% as well as the  overall trade value by 20%.  That is the boost as the Ecumenopolis Commercial designation.

Additionally, Trade Districts and Commercial Segments now provide more Merchant jobs and fewer Clerk jobs as long as the colony designation is Trade Station or Commercial Ring World respectively.  But wait, there's more!  Empires with the Merchant Guilds civic will find that more Merchants replace Clerks.  But wait, there's _even_ more!  Megacorps replace some Clerks with an Executive(s) and Manager(s).  And if that wasn't enough, we'll throw in positive interaction with the "Commercial Enterprise" tradition for another/more Merchant(s) and the "Interstellar Franchising" tradition for another/more Clerk(s) or Manager(s).

# Changes

Overwrites the Trade Station and Commercial Ring World colony designations and the Trade District (for both habitats and the special district for Origin: Shattered Ring) and Commercial Segment district.  The colony designations enable some job swaps from Clerks to Merchants (extra swaps with the "Commercial Enterprise" tradition).  The designations also provide a small amount of bonus trade if you meet varying hidden, trade-related conditions - see if you can figure them out.  The districts themselves also swap jobs if the owner has Civic: Merchant Guilds, Civic: Corporate Dominion (for people who don't own Megacorp), and Megacorps.

Also updates the regular City districts to provide part of a Merchant or Executive job for Trade Guilds, Corporate Dominions, or Megacorps as appropriate when combined with the "Commercial Enterprise" tradition.  Ringworld city segments no longer receive bonus clerks from the "Interstellar Franchising" tradition - instead, those clerk jobs are provided by the commercial segments.

## Localisation

* English by corsairmarks (author)
* Polish (Polskie) by [Gatzek](https://steamcommunity.com/profiles/76561198440146604)

## Compatibility

Overwrites the `col_city`, `col_habitat_trade`, and `col_ring_trade` colony types and existing trade-related districts: `district_city`, `district_srw_commercial`, `district_hab_commercial`, `district_rw_city`, and `district_rw_commercial`.  Despite vastly improved compatibility via Stellaris version 3.3 "Libra," this mod remains separate from [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) because viewing Commercial Arcologies now requires a UI mod, and this mod does not.

This mod will not work well with other mods that make changes to the same colony designations or districts.  Overhaul mods commonly make changes to districts, but are more likely to overwrite the entire file.  Due to how Stellaris file-loading works, change from this mod will overwrite code from full-file district overwrites and apply the verion of commercial districts from this mod.  That's good for thi mod, but could interfere with other modifications bade by other mods.

Compatible with Planetary Diversity.

Built for Stellaris version 3.3 "Libra."  Not compatible with achievements.

### Recommended Companion Mods

[Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) to add a trade-focused colony designation and district to ecumenopolis worlds.

### When to Install

This mod can be safely added to your savegame after the game has started.  Because it adds gameplay objects, it should not be removed during a game.

### Known Issues

Overwriting a colony type or district produces an error log.  Expect to see eight entries in error.log similar to these:

```
[00:24:04][game_singleobjectdatabase.h:147]: Object with key: district_city already exists, using the one at  file: common/districts/10_trade_district_enhancements_urban_district_overrides.txt line: 5
[00:24:04][game_singleobjectdatabase.h:147]: Object with key: district_srw_commercial already exists, using the one at  file: common/districts/10_trade_district_enhancements_urban_district_overrides.txt line: 169
[00:24:04][game_singleobjectdatabase.h:147]: Object with key: district_hab_commercial already exists, using the one at  file: common/districts/13_trade_district_enhancements_habitat_district_overrides.txt line: 5
[00:24:04][game_singleobjectdatabase.h:147]: Object with key: district_rw_city already exists, using the one at  file: common/districts/14_trade_district_enhancements_ringworld_district_overrides.txt line: 8
[00:24:04][game_singleobjectdatabase.h:147]: Object with key: district_rw_commercial already exists, using the one at  file: common/districts/14_trade_district_enhancements_ringworld_district_overrides.txt line: 116
[00:24:05][game_singleobjectdatabase.h:147]: Object with key: col_city already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 10
[00:24:05][game_singleobjectdatabase.h:147]: Object with key: col_habitat_trade already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 128
[00:24:05][game_singleobjectdatabase.h:147]: Object with key: col_ring_trade already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 357
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Improved colony automation plans
* 1.0.2 Adjust colony designation weighting
* 1.1.0 Update for compatibility with Stellaris 3.2.1 "Herbert" - integrate base game changes
* 1.1.1 Mark as compatible with Stellaris version 3.2.2 "Herbert" - the game patch had no script changes
* 1.2.0 Apply colony designation exclusions from Planetary Diversity
    * Special thanks to Gatzek for help with the correct special `district_set`s
    * Add Polish localisation by Gatzek
* 2.0.0 Update for Stellaris version 3.3 "Libra"
    * Districts are no longer full-file overwrites!
    * Now only the five relevant districts are overridden
        * `district_city`
        * `district_srw_commercial`
        * `district_hab_commercial`
        * `district_rw_city`
        * `district_rw_commercial`
    * Update colony automation overrides to account for Permanent Employment
    * Integrate additional changes from 3.3 to overridden content

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/trade_district_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.