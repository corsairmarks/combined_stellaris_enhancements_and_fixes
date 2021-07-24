# Overview

This mod is a compilation of most of my other fixes and balance mods.  Please see the description of each individual mod for what the effects are.

Individual mods update first, then changes are merged here.

# Bundled Mods

This is a bundle of mods to resolve compatibility issues if you want to use them all together.  Please check each individual mod for the effects and any known issues.  The large hex strings are the commit hashes - that is mostly for my own record-keeping to know what revision of the other source code is contained here.

* [Retain Leaders from Integrated Subjects](https://steamcommunity.com/sharedfiles/filedetails/?id=2553818684) ([Source](https://github.com/corsairmarks/keep_leaders_from_integrated_subjects) 2ed59b680e1121866f9ac6ae7f34fa4d84302faf)
* [Leader Traits: Enhanced Randomisation](https://steamcommunity.com/sharedfiles/filedetails/?id=2553806265) ([Source](https://github.com/corsairmarks/leader_trait_randomisation_enhancement) a962fee486c6d062f9d3ea9fe7801767daa4ba67)
* [Restored Content: Fungoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2548834941) ([Source](https://github.com/corsairmarks/portrait_unlock_fungoid) a9680961b4bf4370d7b958eb9d290dba69cea4e1)
* [Yet Another Planetary Sky Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2527918521) ([Source](https://github.com/corsairmarks/yet_another_planetary_sky_fix) 0933af2894d3f7ec772f7de81c334e490849b340)
* ["Agrarian" Idyll for Lithoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2510669821) ([Source](https://github.com/corsairmarks/agrarian_idyll_lithoid) b0beff2b169f818a36f39065113f9501f8af9d67)
* [Ringworld Origin Rebalance for 3.0.*](https://steamcommunity.com/sharedfiles/filedetails/?id=2499901978) ([Source](https://github.com/corsairmarks/ringworld_origin_rebalance) d1f3e1fd53104dc13e261c3bb046f30cbb04523a)
* [Leader Traits: All Eligible Species Traits](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295) ([Source](https://github.com/corsairmarks/enable_all_species_traits_for_leaders) 8e02c9aa1a9d985846ef6ea616264d64518a6714)
* [Leader Traits: Scientist AI Assistant Upgrader](https://steamcommunity.com/sharedfiles/filedetails/?id=2498166286) ([Source](https://github.com/corsairmarks/scientist_ai_assistant_upgrader) df600ad6e737f56144aaa7ea596c9f8b763b58c7)
* [Prosperity Tradition Rebalance for 3.0.3](https://steamcommunity.com/sharedfiles/filedetails/?id=2497266630) ([Source](https://github.com/corsairmarks/prosperity_tradition_rebalance) 5ebe0a0ba146bce8792be411276bae186fa620fe)
* [Full Military Service for Battle Thralls](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357447) ([Source](https://github.com/corsairmarks/battle_thrall_military_leaders) cc568598e38d18d97b491562541340d9f2cff7f0)
* [Planetary Modifier Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357128) ([Source](https://github.com/corsairmarks/planetary_modifier_enhancements) 7bce0431a890e1b2afb6dde533d8194577f1a6cf)
* [Primitive Conquest Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2488154830) ([Source](https://github.com/corsairmarks/primitive_conquest_enhancements) afd75e8c4728c7e7fd5150f0705df9255631b2f7)
* [Technician Job Priority Fix for Slaves](https://steamcommunity.com/sharedfiles/filedetails/?id=2484702578) ([Source](https://github.com/corsairmarks/technician_slave_fix)) - this mod is not actually merged via `git`, but the same 1-character change is present in this one
* [Space Fauna Multiple Resolutions Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2470984445) ([Source](https://github.com/corsairmarks/space_fauna_resolutions_fix) 3f22ec7b060a146fb30a8451f135fe5b742d7e8c)
* [Manifesti 'Personal Autonomy for Munitions' Demand Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2470975831) ([Source](https://github.com/corsairmarks/manifesti_fix) 12ecdce87fde0ebf7c04302e1d0dd4fe4a76a004)

## Source Code

Hosted on [Github](https://github.com/corsairmarks/combined_stellaris_enhancements_and_fixes)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.

## Methodology

Each of the source repositories above is added as a remote to this repository on my local machine.  I fetch all the repositories, then merge them into the `master` branch of this repository.

1. `git remote add <friendly-remote-name> <repo-url>`
2. `git fetch --all -n` to get all the commits, but not the tags
3. `git checkout master` (stash if you need to beforehand)
4. `git merge --no-commit --allow-unrelated-histories -m "merge version 1.2.3 from another repo" <friendly-remote-name>/<branch or commit hash>` (`--allow-unrelated-histories` is only required the first time an unrelated tree, i.e. new remote repo, is added - the first merge commit establishes history between the trees)
5. Solve merge conflicts, if any
6. `git merge --continue`

# Compatibility

Requires Stellaris 3.0.3 and disables achievements.

Check each of the contained mods for an explicit list of incompatibility notes.  Generally, this mod is incompatible with other mods that change worker jobs or built-in special event jobs, districts, the Full Military Service species right, (most) society technologies, or changes to the Prosperity tradition.

## Recommended Companion Mods

The standard planet view has a very small graphic representing your planet's environment and its sky, and so sometimes it is hard to see the alternate sky backgrounds.  This is particularly true for the temperate planets: tropical, continental, and ocean.  To solve that, I _**highly**_ recommend you use [Planetary Diversity - Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1866576239) to expand the viewport.  As a graphics-only mod, it can be added or removed at any time.  It is also stand-alone, so it is not required to use the rest of [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).

## When to Install

This mod should not be removed from your save game.  Some added modifiers and technologies will not work without the changes in this mod.  You can add it safely to already-started games but you will miss out on some of the game-start-time changes (such as Ringworld preference for Driven Assimilators/Rogue Servitors with Shattered Ring, or the updated version of the Extensive Moon System modifier applying to all moons around a gas giant with the modifier).

## Changelog

* 1.0.0 Initial version
* 1.0.1 Fix effect file location (breaking bug), enhance documentation and thumbnail image
* 1.1.0 Upstream updates
    * Integrate "Yet Another Planetary Sky Fix" at version 1.0.2
    * Update from "Full Military Service for Battle Thralls"
* 1.2.0 Apply fix from "Yet Another Planetary Sky Fix" version 1.1.0
* 1.3.0 Update merged mods:
    * "Agrarian" Idyll for Lithoids at 1.4.0
    * Ringworld Origin Rebalance for 3.0.* at 1.0.3
    * Leader Traits: All Eligible Species Traits at 1.3.0 (formerly Enable All Eligible Species Traits for Leaders)
    * Leader Traits: Scientist AI Assistant Upgrader at 1.0.4 (formerly Scientist AI Assistant Upgrader)
    * Prosperity Tradition Rebalance for 3.0.3 at 1.2.0
    * Full Military Service for Battle Thralls at 1.4.0
    * Planetary Modifier Enhancements at 2.3.0
    * Primitive Conquest Enhancements at 1.3.0
    * Add mod: Restored Content: Fungoids at 1.0.1
    * Add mod: Leader Traits: Enhanced Randomisation at 1.0.0
    * Add mod: Retain Leaders from Integrated Subjects at 1.0.1
* 1.3.1 Update merged mods:
    * Full Military Service for Battle Thralls at 1.5.0
    * Retain Leaders from Integrated Subjects at 1.0.2
    * 