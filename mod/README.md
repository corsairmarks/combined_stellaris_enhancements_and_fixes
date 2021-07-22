# Overview

This mod is a compilation of most of my other fixes and balance mods.  Please see the description of each individual mod for what the effects are.

<<<<<<< HEAD
Individual mods update first, then changes are merged here.
=======
And yes, I totally made up "lithorian" as an alternative to "agrarian" - going to stick with it for now.
>>>>>>> agrarian-idyll-lithoid/master

# Bundled Mods

This is a bundle of mods to resolve compatibility issues if you want to use them all together.  Please check each individual mod for the effects and any known issues.  The large hex strings are the commit hashes - that is mostly for my own record-keeping to know what revision of the other source code is contained here.

* [Yet Another Planetary Sky Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2527918521) ([Source](https://github.com/corsairmarks/yet_another_planetary_sky_fix) 0933af2894d3f7ec772f7de81c334e490849b340)
* ["Agrarian" Idyll for Lithoids](https://steamcommunity.com/sharedfiles/filedetails/?id=2510669821) ([Source](https://github.com/corsairmarks/agrarian_idyll_lithoid) b0beff2b169f818a36f39065113f9501f8af9d67)
* [Ringworld Origin Rebalance for 3.0.*](https://steamcommunity.com/sharedfiles/filedetails/?id=2499901978) ([Source](https://github.com/corsairmarks/ringworld_origin_rebalance) 222cac5bf8773b5398f820b86440d38dc4f306df)
* [Enable All Eligible Species Traits for Leaders](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295) ([Source](https://github.com/corsairmarks/enable_all_species_traits_for_leaders) 55f7bf9dc22ad04adeed60b9bd2191f953f4d766)
* [Scientist AI Assistant Upgrader](https://steamcommunity.com/sharedfiles/filedetails/?id=2498166286) ([Source](https://github.com/corsairmarks/scientist_ai_assistant_upgrader) 25b4d8d2ecc9c52bb3de453746cc18b49be294d6)
* [Prosperity Tradition Rebalance for 3.0.3](https://steamcommunity.com/sharedfiles/filedetails/?id=2497266630) ([Source](https://github.com/corsairmarks/prosperity_tradition_rebalance) fc94927d067d203e9a4376ddada18ffc5e73a07b)
* [Full Military Service for Battle Thralls](https://steamcommunity.com/sharedfiles/filedetails/?id=2496357447) ([Source](https://github.com/corsairmarks/battle_thrall_military_leaders) 9b434ab3da658e0208401ea39aaaeec2726f1157)
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

Check each of the contained mods for an explicit list of incompatibility notes.  Generally, this mod is incampatible with other mods that change worker jobs or built-in special event jobs, the Full Military Service species right, (most) society technologies, or changes to the Prosperity tradition.

## Recommended Companion Mods

<<<<<<< HEAD
The standard planet view has a very small graphic representing your planet's environment and its sky, and so sometimes it is hard to see the alternate sky backgrounds.  This is paricularly true for the temperate planets: tropical, continental, and ocean.  To solve that, I _**highly**_ recommend you use [Planetary Diversity - Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1866576239) to expand the viewport.  As a graphics-only mod, it can be added or removed at any time.  It is also stand-alone, so it is not required to use the rest of [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).
=======
* 1.0.0 Initial version
* 1.1.0 Added missing compatibility notes, added Agrarian Idyll amenities to special event jobs
    * `titan_hunter` is in the `planet_farmers` resource category and already had code for amenities-related weighting for Agrarian Idyll, but lacked the actual amenities production for Agrarian Idyll (non-lithoid)
    * `cave_cleaner` is in the `planet_miners` resource category so it made sense to also apply amenities to it
    * purposely did not add agrarian idyll code to the potentially other relevant special job `ratling_scavenger` because it isn't for default countries
* 1.2.0 Include technician fix from [Technician Job Priority](https://steamcommunity.com/sharedfiles/filedetails/?id=2484702578)
* 1.2.1 Fix spelling errors in README (no script changes)
* 1.2.2 Add note about incompatibilities with mods that change Society technologies (no script changes)
* 1.3.0 Add event to flag mod as installed
    * Added README information about adding/removing from a game
    * Add Steam description as text
* 1.3.1 Remove extra images files to keep distribution lightweight
* 1.4.0 Maintenance release
    * Remove monthly pulse event, add flag instead when single player games are loaded
    * Use a more "rocky" icon for Lithorian Utopias (housing tech)
    * Ensure any farming districts created during capitol planet setup are converted to mining districts
>>>>>>> agrarian-idyll-lithoid/master

## Post-Game Start

<<<<<<< HEAD
This mod should not be removed from your save game.  Some added modifiers and technologies will not work without the changes in this mod.  You can add it safely to already-started games but you will miss out on some of the game-start-time changes (such as Ringworld preference for Driven Assimilators/Rogue Servitors with Shattered Ring, or the updated version of the Extensive Moon System modifier applying to all moons around a gas giant with the modifier).
=======
Hosted on [Github](https://github.com/corsairmarks/agrarian_idyll_lithoid)
>>>>>>> agrarian-idyll-lithoid/master

## Changelog

<<<<<<< HEAD
* 1.0.0 Initial version
* 1.0.1 Fix effect file location (breaking bug), enhance documentation and thumbnail image
* 1.1.0 Upstream updates
    * Integrate "Yet Another Planetary Sky Fix" at version 1.0.2
    * Update from "Full Military Service for Battle Thralls"
* 1.2.0 Apply fix from "Yet Another Planetary Sky Fix" version 1.1.0
* 1.3.0 Update merged mods:
    * Primitive Conquest Enhancements 1.3.0
=======
It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.
>>>>>>> agrarian-idyll-lithoid/master
