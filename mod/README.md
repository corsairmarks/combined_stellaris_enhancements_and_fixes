# Overview

Do you wish your Trade Capital, Trade Stations, and Commercial Ring Worlds had a little more "oomph?"  Or maybe you're disappointed with how far ahead Ecumenopolis Commercial Worlds got with my mod [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991).  Then this mod is for you!  The Trade Capital, Trade Station, and Commercial Ring World colony designations now also boost the build-speed of commercial buildings and the relevant commercial districts by 25% as well as the overall trade value by 20%.  That is the same boost as the Ecumenopolis Commercial designation.

Additionally, Trade Districts and Commercial Segments now provide more Merchant jobs and fewer Clerk jobs as long as the colony designation is Trade Station or Commercial Ring World respectively.  But wait, there's more!  MegaCorps and empires with the Merchant Guilds civic will find that more Merchants replace Clerks.  But wait, there's _even_ more!  On ringworld Commercial Segments, MegaCorps replace a Clerk with a Manager and another Clerk with an Executive (all those Clerks need bossing around).  And if that wasn't enough, we'll throw in positive interaction with the "Commercial Enterprise" tradition for another/more Merchant(s) and the "Trickle Up Economics" tradition for another/more Clerk(s).

# Changes

Overwrites the Trade Capital, Trade Station, and Commercial Ring World colony designations and the Trade District (for both habitats and the special district for Origin: Shattered Ring) and Commercial Segment district.  The colony designations enable some job swaps from Clerks to Merchants (extra swaps with the "Commercial Enterprise" tradition).  The designations also provide a small amount of bonus trade if you meet varying hidden, trade-related conditions - see if you can figure them out.  The districts themselves also swap jobs if the owner has Civic: Merchant Guilds, Civic: Corporate Dominion (for people who don't own MegaCorp), and MegaCorps.

Also updates the regular City districts to provide part of a Merchant or Executive job for Merchant Guilds, Corporate Dominions, or MegaCorps as appropriate when combined with the "Commercial Enterprise" tradition.  Ringworld city segments no longer receive bonus clerks from the "Trickle Up Economics" tradition - instead, those clerk jobs are provided by the Commercial Segments.

## Localisation

* English by corsairmarks (author)
* Polish (Polskie) by [Gatzek](https://steamcommunity.com/profiles/76561198440146604)

## Compatibility

Overwrites the `col_city`, `col_capital_trade`, `col_habitat_trade`, and `col_ring_trade` colony types and existing trade-related districts: `district_city`, `district_srw_commercial`, `district_hab_commercial`, `district_rw_city`, and `district_rw_commercial`.  This mod is separate from [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) because viewing Commercial Arcologies requires a UI mod, and this mod does not.

This mod will not work well with other mods that make changes to the same colony designations or districts.  Overhaul mods commonly make changes to districts, but are more likely to overwrite the entire file.  Due to how Stellaris file-loading works, change from this mod will overwrite code from full-file district overwrites and apply the version of commercial districts from this mod.  That's good for this mod, but could interfere with other modifications made by other mods.

Compatible with Planetary Diversity and Gigastructural Engineering (does not modify Gigas districts, but does exclude these districts from spawning on the wrong things).

Built for Stellaris version 3.8 "Gemini."  Not compatible with achievements.

### When to Install

This mod can be safely added to your savegame after the game has started.  Because it adds gameplay objects, it should not be removed during a game.

### Recommended Companion Mods

* [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) to add a trade-focused colony designation and district to ecumenopolis worlds
* [Specialist Subject: Mercatorum](https://steamcommunity.com/sharedfiles/filedetails/?id=2962066593) add a trade-focused specialist subject that will benefit from more sources of trade

## Known Issues

Overwriting a colony type or district produces an error log.  Expect to see nine entries in error.log similar to these:

```
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: district_city already exists, using the one at  file: common/districts/10_trade_district_enhancements_urban_district_overrides.txt line: 5
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: district_srw_commercial already exists, using the one at  file: common/districts/10_trade_district_enhancements_urban_district_overrides.txt line: 158
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: district_hab_commercial already exists, using the one at  file: common/districts/13_trade_district_enhancements_habitat_district_overrides.txt line: 5
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: district_rw_city already exists, using the one at  file: common/districts/14_trade_district_enhancements_ringworld_district_overrides.txt line: 8
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: district_rw_commercial already exists, using the one at  file: common/districts/14_trade_district_enhancements_ringworld_district_overrides.txt line: 117
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: col_city already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 10
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: col_habitat_trade already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 66
[00:52:16][game_singleobjectdatabase.h:165]: Object with key: col_ring_trade already exists, using the one at  file: common/colony_types/01_trade_district_enhancements_colony_type_overrides.txt line: 98
[00:52:17][game_singleobjectdatabase.h:165]: Object with key: has_trade_designation already exists, using the one at  file: common/scripted_triggers/10_trade_district_enhancements_scripted_triggers_ai_overrides.txt line: 2
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
    * Add compatibility for Gigastructural Engineering: districts from this mod are prohibited on gigastructures, habitat-specific districts from this mod are allowed on Interstellar habitats and Gas Giant Habitats
* 2.0.1 Add global flag to indicate that this mod is installed
* 3.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Integrate underlying district changes
    * Better code for the trade-based colony designations
    * Use memory optimization feature for triggers
    * Replace old automation with an enhanced version of the new trade colony plan
    * Add automation specifically for Commercial Shattered Ring Worlds
    * Trade colony designations now indicate that they improve the relevant trade district type
* 3.1.0 Balance update - reduce the overwhelming **Trade Power™** generated for minimal effort and also simplify triggered job swaps
    * Update support for Planetary Diversity and Gigastructural Engineering
    * Reduce the amount of free MegaCorp job swaps; post-unity-rework they are much more powerful than in the past
    * City districts grant 1 Merchant job per 4 districts for regular and MegaCorp empires, instead of substituting Executives for MegaCorps
    * Simplify the Merchant/Executive/Manager jobs swaps for commercial districts - things got a little out of hand
    * Add custom descriptions to the commercial districts, describing the job shift(s)
* 3.2.0 The Urban World colony designation requirements more accurately reflect the base game: it can be used on any planet which is not an ecumenopolis, habitat, or ringworld
* 4.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Bonus clerk jobs are now tied to the tradition Trickle Up Economics instead of Interstellar Franchising
    * Add override of new built-in trigger `has_trade_designation`, consume it for trade colony automation
    * Trade planet automation cooperates with my other trade-related district mods
    * Integrate underlying automation plan and colony designation changes
    * Integrate underlying district changes
* 5.0.0 Compatibility triggers
    * Add a compatibility trigger for other mods to check whether this one is active
    * Consume the compatibility trigger from another mod
    * Remove old compatibility global flag
* 5.1.0 Improve built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)
* 6.0.0 Update for Stellaris version 3.7 "Canis Minor" - integrate underlying game changes
* 6.0.1 Adjust dynamic building weight - custom and overridden colony types now value building the same as built-in colony types
* 6.0.2 Improve built-in support for Planetary Diversity (support warform planets)
* 7.0.0 Update for Stellaris version 3.8 "Gemini"
    * Integrate underlying game changes
    * Add an override of the new "Trade Capital" colony designation - add all the related bonuses from the enhanced trade designations
    * Account for the new "Trade Capital" colony designation in enhanced trade districts
* 7.0.1 Make code more flexible, where possible, with primitive country types

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/trade_district_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.