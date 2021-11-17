# Overview

Does your species prefer the warm glow of an irradiated planet?  Whether you "accidentally" nuked your homeworld or evolved to feed on radiation, this mod will help you ~~bombard~~ "terraform" planets into tomb worlds.  This includes applying orbital bombardment graphics to any planet being "terraformed" to a tomb world.

# Changes

Adds terraforming links to change almost any colonizable, non-artificial planet into a tomb world (`pc_nuked`).  Empires whose founder species has one (or more) of the Tomb World Preference, Survivor, Radiotrophic, or Irradiated traits (nuked empires) do not require any special technologies to "terraform" into tomb worlds.  Non-nuked empires must have at least 1 Pop of a nuked species and the Tomb World Adaptation technology.  Converting unhabitable worlds (barren, cold barren, or frozen) that have the Terraforming Candidate modifier always requires the Climate Restoration technology.

These new terraforming links allowing them to "terraform" planets into tomb worlds.  Supported "terraforming" transformations:

* All nine basic habitable planet classes plus gaia planets
    * One-quarter the normal cost to terraform a world into a different category (e.g. dry to wet or cold)
    * Nuked empires and Memorialists can use tomb world "terraforming" without first researching Terrestrial Sculpting
    * Non-nuked empires must have at least one Pop of a nuked species as well as the Terrestrial Sculpting and Tomb World Adaptation technologies
    * Shows the planetary bombardment graphics while "terraforming"
* Hive and machine worlds
    * One-half the normal cost to terraform a world into a different category (requires more ~~bombs~~ "terraforming devices" to remove)
    * Nuked empires and Memorialists can use tomb world "terraforming" without first researching Terrestrial Sculpting
    * Non-nuked empires must have at least one Pop of a nuked species as well as the Terrestrial Sculpting and Tomb World Adaptation technologies
    * Shows the planetary bombardment graphics while "terraforming"
* Barren/cold barren/frozen worlds with the "Terraforming Candidate" modifier
    * Standard cost for barren
    * Standard high cost for cold barren/frozen
    * Requires Climate Restoration technology

Planets converted to tomb worlds this way are not eligible for the random events that can sometimes occur on tomb worlds - there's no mystery about what happened, it was ~~bombed~~ "terraformed" on purpose.  Non-nuked empires that have already "terraformed" a planet into a tomb world waive the requirement to have at lease one nuked Pop.

## Compatibility

Built for Stellaris version 3.1.\* "Lem."  Not compatible with achievements.

Only adds new terraforming links, so it should not conflict with other mods that do not also add terraforming links from and to the same planet classes.  Does not support new planet classes added by mods such as Planetary Diversity, but will still work for the base game's planet classes.

## Changelog

* 1.0.0 Initial version
* 1.1.0 Remove Terrestrial Sculpting as a prerequisite for "nuked" empires - you can "terraform" worlds into tomb worlds at game start
* 1.2.0 Memorialist (all types) are now included, but the Memorialist AIs won't use it
* 1.2.1 Decrease overlap in effects when installed with [Aesthetic Terraform Stations](https://steamcommunity.com/sharedfiles/filedetails/?id=2622411084)
* 1.2.2 Help the AI calm down about terraforming to tomb worlds - these conditions make the AI likely to terraform to a tomb world
    * Owner is a nuked species and the planet is not colonized
    * Owner is a nuked species and over 60% of Pops are a nuked species (excludes non-sapient pops and undesirables)
    * Over 80% of Pops are a nuked species (excludes non-sapient pops and undesirables)
    * Terraforming Candidate and the empire's main species is nuked
    * Never for Gaia worlds
* 1.2.3 Machine World and Hive World terraform to Tomb World should check Pop percentage of the planet, not empire

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/terraform_to_pc_nuked)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.

# Special Thanks

Inspired by [Tomb World 'Terraforming'](https://steamcommunity.com/sharedfiles/filedetails/?id=2311769287) by [SingABrightSong](https://steamcommunity.com/id/singabrightsong/myworkshopfiles/?appid=281990) and the new Radiotrophic trait added in Stellaris 3.1 for owners of the Plantoids Species Pack. Radiotrophic plantoid and fungoid species have decreased upkeep cost and a population growth rate increase on tomb worlds, so would also benefit from the ability to "create" tomb worlds.  The original mod has not been updated, so I created this enhanced and expanded version.