# Overview

Have you ever noticed that some habitable planet classes, when they are moons, will display the parent planet in the sky in the planet view (with rings, if it has them)?  Do you wish that all habitable moons had this feature instead of just a few?  This mod is for you.

The artwork is already present in `common/gfx/portraits/environments`, it just isn't enabled for all planet classes which have art.  These planet classes already use the fancy sky art:

* Arid (`pc_arid`)
* Savannah (`pc_savannah`)
* Arctic (`pc_arctic`)
* Alpine (`pc_alpine`)
* Ecumenopolis (`pc_city`)

Note that Tomb Worlds (`pc_nuked`) do not have fancy sky art available.

## Notes

There are probably lots of other mods that make this same change, but I made this one with the express purpose of merging it in to [Subtle Polish](https://steamcommunity.com/sharedfiles/filedetails/?id=2522974089).

# Changes

No gameplay changes.  This mod updates several of the default planet classes, where the only change is to set `uses_alternative_skies_for_moons = yes`.

* Desert (`pc_desert`)
* Tropical (`pc_tropical`)
* Continental (`pc_continental`)
* Ocean (`pc_ocean`)
* Tundra (`pc_tundra`)
* Gaia (`pc_gaia`)

## Compatibility

In order to change the default planet classes without impacting habitability (i.e. breaking it), it is necessary to override the entire `common/planet_classes/00_planet_classes.txt` file.  What this means to you is that this mod is incompatible with other mods that need to override the default habitable planet classes.

Fully compatible with [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835) and [Ancient Cache of Technologies](https://steamcommunity.com/sharedfiles/filedetails/?id=1419304439) because those mods do not overwrite the built-in planetary classes.

**Not** compatible with [Real Space](https://steamcommunity.com/sharedfiles/filedetails/?id=937289339), but that mod already activates the same art so you don't need this one.

Built for Stellaris version 3.2.* "Herbert."  **Not** compatible with achievements. Why? Planet classes are a gameplay object, even though the ultimate effect of this mod is cosmetic only.

### Verifying Mod Compatibility

You can verify mod compatibility yourself very easily.  Steam downloads mods into a directory in your Steam library (if you have more than one, mods go into the one with their corresponding game).  Inside the library (the default is at `C:/Program Files (x86)/Steam/steamapps`), browse to `steamapps/workshop/content/281990` (281990 is the Steam ID of Stellaris).

Inside this folder, you will see many directories named with just numbers.  Those numbers are Steam Mod IDs - you can find a mod's ID easily from its Workshop web address.  For example, this mod's Workshop page is at https://steamcommunity.com/sharedfiles/filedetails/?id=2527918521 so its ID is 2527918521.  What you need to do is find the ID of the mod(s) you want to check for compatibility - then open their directories.

Inside each mod you want to check, browse to the `common/planet_classes` directory.  If you see a file named `00_planet_classes.txt` then that mod is _not_ compatible with this one.  Otherwise there should not be a conflict - that's the only code file contained in this mod.

### When to Install

This mod can be safely added or removed from your savegame at any time.

### Recommended Companion Mods

The standard planet view has a very small graphic representing your planet's environment and its sky, and so sometimes it is hard to see the alternate sky backgrounds.  This is particularly true for the temperate planets: tropical, continental, and ocean.  To solve that, I _**highly**_ recommend you use [Planetary Diversity - Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1866576239) to expand the viewport.  As a graphics-only mod, it can be added or removed at any time.  It is also stand-alone, so it is not required to use the rest of [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).

[Bigger Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1587178040) or [UI Overhaul Dynamic](https://steamcommunity.com/sharedfiles/filedetails/?id=1623423360) also provide expanded planetview graphics.

## Changelog

* 1.0.0 Initial version
* 1.0.1 Better thumbnail
* 1.0.2 Fix filename misspelling
* 1.1.0 Switch to entire-file override for 00_planet_classes.txt
* 2.0.0 Updated for Stellaris version 3.1 "Lem" - no changes to what the mod does, just integrated the underlying game changes
* 2.1.0 Mark compatible with Stellaris version 3.2 "Herbert" - no script changes

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/yet_another_planetary_sky_fix)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.