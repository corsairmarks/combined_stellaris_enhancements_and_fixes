# Overview

Does your species prefer the warm glow of an irradiated planet?  Whether you "accidentally" nuked your homeworld or evolved to feed on radiation, this mod will help you ~~bombard~~ "terraform" planets into tomb worlds.  This includes applying orbital bombardment graphics to any planet being "terraformed" to a tomb world.

As of Stellaris version 3.5 "Fornax" and the Toxoids expansion, the game has built-in a variation of terraforming planets to tomb worlds, but only for empires that are Relentless Industrialists and only after having completed a special project. This mod allows all empires to access it with a lower cost, but with higher research prerequisites. Thus you may rarely see two options to change a planet into a tomb world if your empire has the Relentless Industrialists study completed - that is a feature and not a bug.

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
* Barren/cold barren/frozen/toxic worlds with the "Terraforming Candidate" modifier
    * Standard cost for barren/toxic
    * Standard high cost for cold barren/frozen
    * Requires Climate Restoration technology
    * From frozen also requires the "Hydrocentric" ascension perk
    * From toxic also requires the "Detox" ascension perk

Planets converted to tomb worlds this way are not eligible for the random events that can sometimes occur on tomb worlds - there's no mystery about what happened, it was ~~bombed~~ "terraformed" on purpose.  Non-nuked empires that have already "terraformed" a planet into a tomb world waive the requirement to have at lease one nuked Pop.

## Compatibility

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

Only adds new terraforming links, so it should not conflict with other mods that do not also add terraforming links from and to the same planet classes.  Does not support new planet classes added by mods such as Planetary Diversity, but will still work for the base game's planet classes.

### Recommended Companion Mods

["Terraform" to Tomb World: Planetary Diversity Compatibility](https://steamcommunity.com/workshop/filedetails/?id=2766967251) adds support for planet classes added by Planetary Diversity.  Almost all of them can now be "terraformed" into Tomb Worlds.

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
* 2.0.0 Upgrade for compatibility with Stellaris version 3.2 "Herbert"
    * Use new resource syntax for terraform links
    * Account for the `trait_harvested_radiotrophic` trait
    * Re-weight `pc_nuked` terraform links to be of similar weight to the newly-re-weighted built-in terraform links
    * Pop % for the AI to want to terraform is not 50%/75% nuked empire/non-nuked empire
* 2.1.0 Nanite Worlds now eligible to become Tomb Worlds
    * Add `pc_gray_goo` to `pc_nuked` terraforming link (standard cost - since Nanite Worlds have a flat cost no matter to which type it is terraformed)
    * Improve trigger for determining if a species is "nuked"
* 3.0.0 Update for Stellaris version 3.3 "Libra"
    * Memorialist trigger is built in to the game now, so remove implementation from this mod
    * Fix bug where Terraforming Candidate modifier was not removed when terraforming to a Tomb World
    * Code refactor to support ["Terraform" to Tomb World: Planetary Diversity Compatibility](https://steamcommunity.com/workshop/filedetails/?id=2766967251) - no functionality changes, but the logic is now much easier for the add-on to reuse
* 4.0.0 Update for Stellaris version 3.4 "Cepheus" - use memory optimization feature for effects and triggers
* 5.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Account for new radiotrophic variants
    * Support changes to terraforming frozen worlds (you can still nuke them if they have the `frozen_terraforming_candidate` modifier)
* 5.1.0 Support "terraforming" Toxic worlds to Tomb Worlds with the Detox ascension perk
* 6.0.0 Compatibility triggers
    * Add a compatibility trigger for other mods to check whether this one is active
    * Consume the compatibility trigger from another mod
    * Remove old compatibility global flag

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/terraform_to_pc_nuked)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.

# Special Thanks

Inspired by [Tomb World 'Terraforming'](https://steamcommunity.com/sharedfiles/filedetails/?id=2311769287) by [SingABrightSong](https://steamcommunity.com/id/singabrightsong/myworkshopfiles/?appid=281990) and the new Radiotrophic trait added in Stellaris 3.1 for owners of the Plantoids Species Pack. Radiotrophic plantoid and fungoid species have decreased upkeep cost and a population growth rate increase on tomb worlds, so would also benefit from the ability to "create" tomb worlds.  The original mod has not been updated, so I created this enhanced and expanded version.