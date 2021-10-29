# Overview

Do you wish your Trade Stations and Commercial Ring Worlds had a little more "oomph?"  Or maybe you're disappointed t how far ahead Ecumenopolis Commercial Worlds got with my mod [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991).  Then this mod is for you!  The Trade Station and Commercial Ring World colony designations now also boost the build-speed of commercial buildings and the relevant commercial districts by 25% as well as the  overall trade value by 20%.  That is the boost as the Ecumenopolis Commercial designation.

Additionally, Trade Districts and Commercial Segments now provide more Merchant jobs and fewer Clerk jobs as long as the colony designation is Trade Station or Commercial Ring World respectively.  But wait, there's more!  Empires with the Merchant Guilds civic will find that more Merchants replace Clerks.  But wait, there's _even_ more!  Megacorps replace some Clerks with an Executive(s) and Manager(s).  And if that wasn't enough, we'll throw in positive interaction with the "Commercial Enterprise" tradition for another/more Merchant(s) and the "Interstellar Franchising" tradition for another/more Clerk(s) or Manager(s).

# Changes

Overwrites the Trade Station and Commercial Ring World colony designations and the Trade District (for both habitats and the special district for Origin: Shattered Ring) and Commercial Segment district.  The colony designations enable some job swaps from Clerks to Merchants (extra swaps with the "Commercial Enterprise" tradition).  The designations also provide a small amount of bonus trade if you meet varying hidden, trade-related conditions - see if you can figure them out.  The districts themselves also swap jobs if the owner has Civic: Merchant Guilds, Civic: Corporate Dominion (for people who don't own Megacorp), and Megacorps.

Also updates the regular City districts to provide part of a Merchant or Executive job for Trade Guilds, Corporate Dominions, or Megacorps as appropriate when combined with the "Commercial Enterprise" tradition.  Ringworld city segments no longer receive bonus clerks from the "Interstellar Franchising" tradition - instead, those clerk jobs are provided by the commercial segments.

## Compatibility

Overwrites the `col_city`, `col_habitat_trade`, and `col_ring_trade` colony types and the entirety of the `common/districts/00_urban_districts.txt`, `common/districts/03_habitat_districts.txt`, and `common/districts/04_ringworld_districts.txt` files.  Because overwriting district files presents a large compatibility challenge, I opted to develop this as a separate from [Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) despite the mods providing very similar effects but for different districts.

This mod will not work well with other mods that make changes to habitat or ringworld districts, or that make changes to the same colony designations.  Overhaul mods commonly make changes to districts - and so do some of my other mods!  If you want to play many of my mods together, consider using [Subtle Polish: A Collection of Fixes and Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2522974089) instead - it resolves the incompatibilities between them.

Built for Stellaris version 3.1.2 "Lem."  Not compatible with achievements.

### Recommended Companion Mods

[Colony Designation: Ecumenopolis Commercial](https://steamcommunity.com/sharedfiles/filedetails/?id=2597129991) to add a trade-focused colony designation and district to ecumenopolis worlds.

### When to Install

This mod can be safely added to your savegame after the game has started.  Because it does not add and gameplay objects, it should be safe to remove during a game.  Back up your savegame before trying to remove a mod.

### Known Issues

Overwriting a colony type produces an error log.  Expect to see three entries in error.log similar to these:

```
[00:28:40][game_singleobjectdatabase.h:147]: Object with key: col_city already exists
[00:28:40][game_singleobjectdatabase.h:147]: Object with key: col_habitat_trade already exists
[00:28:40][game_singleobjectdatabase.h:147]: Object with key: col_ring_trade already exists
```

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/trade_district_enhancements)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.