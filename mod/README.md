# Overview

This mod is a compilation of most of my other fixes and balance mods.  Please see the description of each individual mod for what the effects are.

Individual mods update first, then changes are merged here.

# Bundled Mods

This is a bundle of mods to resolve compatibility issues if you want to use them all together.  Please check each individual mod for the effects and any known issues.  The large hex strings are the commit hashes - that is mostly for my own record-keeping to know what revision of the other source code is contained here.

* ["Agrarian" Idyll for Lithoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2510669821) ([Source](https://github.com/corsairmarks/agrarian_idyll_lithoid) a1f17e19b635c6ef3f928cac6b4b893c20a95ecd)
* [Ringworld Origin Rebalance for 3.0.*](https://steamcommunity.com/sharedfiles/filedetails/?id=2499901978) ([Source](https://github.com/corsairmarks/ringworld_origin_rebalance) 222cac5bf8773b5398f820b86440d38dc4f306df)
* [Enable All Eligible Species Traits for Leaders](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295) ([Source](https://github.com/corsairmarks/enable_all_species_traits_for_leaders) 55f7bf9dc22ad04adeed60b9bd2191f953f4d766)
* [Scientist AI Assistant Upgrader](https://steamcommunity.com/sharedfiles/filedetails/?id=2498166286) ([Source](https://github.com/corsairmarks/scientist_ai_assistant_upgrader) 25b4d8d2ecc9c52bb3de453746cc18b49be294d6)
* [Prosperity Tradition Rebalance for 3.0.3](https://steamcommunity.com/sharedfiles/filedetails/?id=2497266630) ([Source](https://github.com/corsairmarks/prosperity_tradition_rebalance) fc94927d067d203e9a4376ddada18ffc5e73a07b)
* [Full Military Service for Battle Thralls](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357447) ([Source](https://github.com/corsairmarks/battle_thrall_military_leaders) cb304752bc44810d22d1535f7af56561efb4c053)
* [Planetary Modifier Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357128) ([Source](https://github.com/corsairmarks/planetary_modifier_enhancements) 8ed533f7eaea813f580c6f380f092ded087f9e7d)
* [Primitive Conquest Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2488154830) ([Source](https://github.com/corsairmarks/primitive_conquest_enhancements) 6aaf42369c1e13720a3fadca89e3058b0aee9580)
* [Technician Job Priority Fix for Slaves](https://steamcommunity.com/sharedfiles/filedetails/?id=2484702578) ([Source](https://github.com/corsairmarks/technician_slave_fix)) - this mod is not actually merged via `git`, but the same 1-character change is present in this one
* [Space Fauna Multiple Resolutions Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2470984445) ([Source](https://github.com/corsairmarks/space_fauna_resolutions_fix) 3f22ec7b060a146fb30a8451f135fe5b742d7e8c)
* [Manifesti 'Personal Autonomy for Munitions' Demand Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2470975831) ([Source](https://github.com/corsairmarks/manifesti_fix) 12ecdce87fde0ebf7c04302e1d0dd4fe4a76a004)

## Source Code

[Hosted on Github](https://github.com/corsairmarks/combined_stellaris_enhancements_and_fixes)

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

Check each of the contained mods for an explicit list of incompatibility notes.  Generally, this mod is incampatible with other mods that change worker jobs or built-in special event jobs, the Full Military Service species right, (most) society technologies, or changes to the Prosperity tradition.

## Post-Game Start

This mod should not be removed from your save game.  Some added modifiers and technologies will not work without the changes in this mod.  You can add it safely to already-started games but you will miss out on some of the game-start-time changes (such as Ringworld preference for Driven Assimilators/Rogue Servitors with Shattered Ring, or the updated version of the Extensive Moon System modifier applying to all moons around a gas giant with the modifier).

## Changelog

* 1.0.0 Initial version
* 1.0.1 Fix effect file location (breaking bug), enhance documentation and thumbnail image