# Overview

Lithoids can pick the Agrarian Idyll civic, but the benefits are still applied to farming districts.  This mod creates a swapped Agrarian Idyll just for lithoids - now your miners will generate amenities instead of farmers!  This mod also features english localisation for these effects.

A new addition for both flavors of Agrarian Idyll should help reduce the need to build cities in 3.0.*: rural districts (generator, mining, or farming) now add one unit of planetary capacity per two districts and one building slot per four districts.  Additionally, the Agrarian/Lithorian Utopias technology doubles these benefits for either farming districts or mining districts depending on whether your empire is lithoid.

And yes, I totally made up "lithorian" as an alternative to "agrarian" - going to stick with it for now.

# Changes

Creates a civic swap for Agrarian Idyll for Lithoids (it will automatically change - similar to Devouring Swarm <-> Terravore).  Miners (_including_ those for mote/gas/crystal deposits) generate the same amount of Amenities that farmers generate for the standard version, and have their job weights adjusted accordingly for traits that affect Amenities output.  A new technology "Lithorian Utopias" replaces the standard "Agrarian Utopias" and adds +1 housing to Mining Districts.  Lithorian Idyll also loses the usual Agrarian Idyll bonus housing on Ringworld Farming Districts.

Rural districts grant 0.5 planetary capacity and 0.25 building slots per district.  The Agrarian/Lithorian Utopias technology doubles these benefits for the appropriate district type (farming or mining).

Because this is a tradition text swap, all the the normal restrictions for Agrarian Idyll apply to it (without further code changes).

## Compatibility

Requires Stellaris version 3.0.3. This mod alters the following core Stellaris files:

* `governments/civics/00_civics.txt` - replaces one civic `civic_agrarian_idyll` (new file `government/civics/01_agrarian_idyll_override.txt`)
* `districts/02_rural_districts.txt` - entire file, excludes farming districts for agrarian idyll lithoids and includes mining districts for them instead
* `districts/04_ringworld_districts.txt` entire file, excludes agrarian idyll lithoids from the farming district benefits (**NOT** compatible with my mod [Prosperity Tradition Rebalance](https://steamcommunity.com/sharedfiles/filedetails/?id=2497266630) because they both affect ringworld districts)
* `pop_jobs/03_worker_jobs.txt` - entire file, adds amenities production to miners, mote miners, gas miners, and crystal miners (but not the specialist refiners) (**NOT** compatible with my mod [Technician Job Priority](https://steamcommunity.com/sharedfiles/filedetails/?id=2484702578) but includes the same fix)
* `pop_jobs/06_event_jobs.txt` - entire file, adds amenities production to cave miners for agrarian idyll lithoids, add amenities to titan hunters for agrarian idyll (non-lithoids); titan hunters were already weighted for this civic
* `technology/00_soc_tech.txt` entire file, excludes lithoids from researching `tech_housing_agrarian_idyll`

Stellaris requires overriding the entire containing file to make changes to a district, job, or technology (there are technical consequences if not). That means this mod is incompatible with other mods that make changes to rural and/or ringworld districts, mods that change worker-strata jobs or special event jobs, and mods that make changes to any Society technologies.

This mod is not compatible with achievements because it overwrites core Stellaris files.

### Post-Game Start

This mod can be safely added after the game has started, but should not be removed from a game in-progress.  Losing access to the new technology "Lithorian Idyll" could cause problems for the game if any countries have researched it.

## Known Issues

Overriding a civic generates an error log. Expect to see one line in the error.log file similar to this:

```
[15:49:52][game_singleobjectdatabase.h:147]: Object with key: civic_agrarian_idyll already exists
```

## Change Log

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
* 1.5.0 Enhance Agrarian/Lithorian Idyll with building slots and carrying capacity bonuses - the goal is to reduce the need for City Districts
    * Rural districts increase building slots and carrying capacity
    * Utopias tech doubles down on these bonuses for Agricultural or Mining Districts (depending on whether you are a lithoid empire)
* 1.5.1 Update images (including thumbnail)

## Source Code

Hosted on [Github](https://github.com/corsairmarks/agrarian_idyll_lithoid)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.