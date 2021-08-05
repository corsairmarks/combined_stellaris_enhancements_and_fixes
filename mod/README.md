# Overview

This mod is a compilation of most of my other fixes and balance mods.  Please see the description of each individual mod for what the effects are.

Individual mods update first, then changes are merged here.

# Major Update

Version 2.0.0 adds a mod that reduces compatibility of this mod.  Because Deassimilate Machines can be incompatible with other assimilation mods, this may cause issues if you are already using such a mod.  You can manually download the most recent version without this breaking change here: [1.3.4](https://github.com/corsairmarks/combined_stellaris_enhancements_and_fixes/releases/tag/1.3.4).  You only need the contents of the `mod` folder for a local install, disregard the other directories and files. You should rename the folder and then copy the entire (renamed) folder into the local `mod` folder.  More instructions on where to install local mods can be found on the [wiki](https://stellaris.paradoxwikis.com/Mods).

# Bundled Mods

This is a bundle of mods to resolve compatibility issues if you want to use them all together.  Please check each individual mod for the effects and any known issues.  The large hex strings are the commit hashes - that is mostly for my own record-keeping to know what revision of the other source code is contained here.

* [Counter-Limited Armies Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2564348666) ([Source](https://github.com/corsairmarks/limited_army_counter_fix) dfe33503bee3c0484e3dba7ec5d31059fcc499a5)
* [Deassimilated Machine Worlds](https://steamcommunity.com/sharedfiles/filedetails/?id=2559702143) ([Source](https://github.com/corsairmarks/deassimilated_machine_worlds) 55764384b73eca3cc54e89820c4ba008e8442458)
* [Deassimilated Machines](https://steamcommunity.com/sharedfiles/filedetails/?id=2553812372) ([Source](https://github.com/corsairmarks/deassimilate_machines) 78ced56c472b7417331337ac36e62eb79598f6b8)
* [Retain Leaders from Integrated Subjects](https://steamcommunity.com/sharedfiles/filedetails/?id=2553818684) ([Source](https://github.com/corsairmarks/keep_leaders_from_integrated_subjects) 26a61cd4f3d426f7b12648238f87bd65d19a3377)
* [Leader Traits: Enhanced Randomisation](https://steamcommunity.com/sharedfiles/filedetails/?id=2553806265) ([Source](https://github.com/corsairmarks/leader_trait_randomisation_enhancement) 528ed549fcbff74592781d5c58061334482e3f2f)
* [Restored Content: Fungoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2548834941) ([Source](https://github.com/corsairmarks/portrait_unlock_fungoid) a9680961b4bf4370d7b958eb9d290dba69cea4e1)
* [Yet Another Planetary Sky Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2527918521) ([Source](https://github.com/corsairmarks/yet_another_planetary_sky_fix) 0933af2894d3f7ec772f7de81c334e490849b340)
* ["Agrarian" Idyll for Lithoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2510669821) ([Source](https://github.com/corsairmarks/agrarian_idyll_lithoid) 8337ab353dd1a6ba0edbb5904572939f6e8c0485)
* [Ringworld Origin Rebalance for 3.0.*](https://steamcommunity.com/sharedfiles/filedetails/?id=2499901978) ([Source](https://github.com/corsairmarks/ringworld_origin_rebalance) d1f3e1fd53104dc13e261c3bb046f30cbb04523a)
* [Leader Traits: All Eligible Species Traits](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295) ([Source](https://github.com/corsairmarks/enable_all_species_traits_for_leaders) bed661ebb09fb98bbbaef466519ed652ec618ce0)
* [Leader Traits: Scientist AI Assistant Upgrader](https://steamcommunity.com/sharedfiles/filedetails/?id=2498166286) ([Source](https://github.com/corsairmarks/scientist_ai_assistant_upgrader) df600ad6e737f56144aaa7ea596c9f8b763b58c7)
* [Prosperity Tradition Rebalance for 3.0.3](https://steamcommunity.com/sharedfiles/filedetails/?id=2497266630) ([Source](https://github.com/corsairmarks/prosperity_tradition_rebalance) 5ebe0a0ba146bce8792be411276bae186fa620fe)
* [Full Military Service for Battle Thralls](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357447) ([Source](https://github.com/corsairmarks/battle_thrall_military_leaders) 55444c031afc8d926dc701c61a326b6b110ecaf4)
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
    * Leader Traits: Enhanced Randomisation at 1.0.1
* 1.3.2 Update merged mod "Agrarian" Idyll for Lithoids at 1.5.1
* 1.3.3 Update merged mods:
    * Leader Traits: All Eligible Species Traits at 1.4.0
    * Leader Traits: Enhanced Randomisation at 1.1.0
* 1.3.4 Update merged mods:
    * Full Military Service for Battle Thralls at 1.5.1
    * Retain Leaders from Integrated Subjects at 1.1.0
* 2.0.0 Add merged mods:
    * Deassimilate Machines at 1.0.1
    * Deassimilated Machine Worlds at 1.0.0
* 2.1.0 Add merged mod: Counter-Limited Armies Fix
* 2.1.1 Update merged mods:
    * Deassimilated Machine Worlds at 1.0.1