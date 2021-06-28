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

No gameplay changes.

## Compatibility

This mod replaces several default planet classes, where the only change is to set `uses_alternative_skies_for_moons = yes`.

* Desert (`pc_desert`)
* Tropical (`pc_tropical`)
* Continental (`pc_continental`)
* Ocean (`pc_ocean`)
* Tundra (`pc_tundra`)
* Gaia (`pc_gaia`)

What this means to you is that this mod is incompatible with other mods that make changes to the above six (6) planet classes.

Compatible with [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835) because it does not overwrite the built-in planetary classes.

**Not** compatible with [Real Space](https://steamcommunity.com/sharedfiles/filedetails/?id=937289339), but it already activates the same art so you don't need this mod.

**Not** compatible with achievements. Why? Planet classes are a gameplay object, even though the ultimate effect of this mod is cosmetic only.

## Changelog

* 1.0.0 Initial version
* 1.0.1 Better thumbnail

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/yet_another_planetary_sky_fix)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.