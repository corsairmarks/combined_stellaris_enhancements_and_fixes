# Overview

Does your species prefer the warm glow of an irradiated planet?  Whether you "accidentally" nuked your homeworld or evolved to feed on radiation, this mod will help you ~~bombard~~ "terraform" planets into tomb worlds.

# Changes

Adds terraforming links for empires whose founder species has one (or more) of the Survivor, Tomb World Preference, Radiotrophic, or Irradiated traits. These new terraforming links allowing them to "terraform" planets into tomb worlds (`pc_nuked`).  Supported "terraforming" transformations:

* All nine basic habitable planet classes plus gaia planets - one-quarter the normal cost, does **not** require a special technology
* Hive and machine worlds - one-half the normal cost, does **not** require a special technology
* Barren/cold barren/frozen worlds with the "Terraforming Candidate" modifier - standard cost for barren, standard high cost for cold barren/frozen, requires Climate Restoration technology

Planets converted to tomb worlds this way are not eligible for the random events that can sometimes occur on tomb worlds - there's no mystery about what happened, it was ~~bombed~~ "terraformed" on purpose.

## Compatibility

Built for Stellaris version 3.1.\* "Lem."  Not compatible with achievements.

Only adds new terraforming links, so it should not conflict with other mods.  Does not support new planet classes added by mods such as Planetary Diversity, but will still work for the base game's planet classes.

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub]()

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.

# Special Thanks

Inspired by [Tomb World 'Terraforming'](https://steamcommunity.com/sharedfiles/filedetails/?id=2311769287) by [SingABrightSong](https://steamcommunity.com/id/singabrightsong/myworkshopfiles/?appid=281990) and the new Radiotrophic trait added in Stellaris 3.1 for owners of the Plantoids Species Pack. Radiotrophic plantoid and fungoid species have decreased upkeep cost and a population growth rate increase on tomb worlds, so would also benefit from the ability to "create" tomb worlds.  The original mod has not been updated, so I created this enhanced and expanded version.