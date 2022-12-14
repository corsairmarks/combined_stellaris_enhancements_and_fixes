# Overview

Lithoids can pick the Agrarian Idyll civic, but the benefits are still applied to farming districts.  This mod creates a swapped Agrarian Idyll just for lithoids - now your miners will generate amenities instead of farmers!  This mod also features english localisation for these effects.

A new addition for both flavors of Agrarian Idyll should help reduce the need to build cities in 3.0 and above: rural districts (generator, mining, or farming) add one building slot per four districts (as of 3.2 farming districts do this in base game).  Additionally, the Agrarian/Lithorian Utopias technology doubles these benefits for either farming districts or mining districts depending on whether your empire is lithoid.

# Changes

Creates a civic swap for Agrarian Idyll for Lithoids (it will automatically change - similar to Devouring Swarm <-> Terravore).  Miners (_including_ those for mote/gas/crystal deposits) generate the same amount of Amenities that farmers generate for the standard version, and have their job weights adjusted accordingly for traits that affect Amenities output.  A new technology "Lithorian Utopias" replaces the standard "Agrarian Utopias" and adds +1 housing to Mining Districts.  Lithorian Idyll also loses the usual Agrarian Idyll bonus housing on Ringworld Farming Districts.

Rural districts grant 0.25 building slots per district.  The Agrarian/Lithorian Utopias technology doubles these benefits for the appropriate district type (farming or mining).

Because this is a tradition text swap, all the the normal restrictions for Agrarian Idyll apply to it (without further code changes).

## Compatibility

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.  This mod overrides one core Stellaris file (`common/districts/02_rural_districts.txt` in order to add +building slot bonuses to all of them), and also overrides a number of built-in game objects at the individual level.  In particular, this mod overrides:

* `civic_agrarian_idyll` to add the alternative description for lithoids
* `civic_corporate_anglers` to remove the restriction on combining it with `civic_agrarian_idyll` (likely a Paradox oversight)
* `district_rw_farming` to excludes Lithorian Idyll from the farming district housing benefits (Agrarian Idyll normally gets +5 housing)
* Many worker-stratum job to ensure the Agrarian Idyll and Lithorian Idyll bonus apply to farming or mining jobs, respectively: `miner`, `crystal_miner`, `gas_extractor`, `mote_harvester`, `farmer`, `scrap_miner`, `angler`, and `manufactorium_scraper`
* Several event-related jobs, for the same reason: `cave_cleaner`, `titan_hunter`, `turtle_miner`
* `tech_housing_agrarian_idyll` in order to exclude Lithorian Idyll, who now have their own version of this technology

This mod avoids overwriting jobs unrelated to the core game mechanic being modified.  It should therefore not conflict with mods that make changes to other worker and event jobs, or other ringworld districts.  It is now only incompatible with mods that want to edit exactly the same game objects (as listed above).

### When to Install

This mod can be safely added after the game has started, but should not be removed from a game in-progress.  Losing access to the new technology "Lithorian Idyll" could cause problems for the game if any countries have researched it.

## Known Issues

Overriding a job, technology, or civic causes the game to log errors. Expect to see sixteen lines in the error.log file similar to these:

```
[17:11:02][technology.cpp:1154]: Duplicate technology: tech_housing_agrarian_idyll
[17:11:02][game_singleobjectdatabase.h:165]: Object with key: district_rw_farming already exists, using the one at  file: common/districts/10_agrarian_idyll_lithoid_ringworld_district_overrides.txt line: 9
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: cave_cleaner already exists, using the one at  file: common/pop_jobs/16_agrarian_idyll_lithoid_event_job_overrides.txt line: 4
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: titan_hunter already exists, using the one at  file: common/pop_jobs/16_agrarian_idyll_lithoid_event_job_overrides.txt line: 81
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: turtle_miner already exists, using the one at  file: common/pop_jobs/16_agrarian_idyll_lithoid_event_job_overrides.txt line: 169
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: manufactorium_scraper already exists, using the one at  file: common/pop_jobs/16_agrarian_idyll_lithoid_event_job_overrides.txt line: 241
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: miner already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 2
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: crystal_miner already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 126
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: gas_extractor already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 213
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: mote_harvester already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 295
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: farmer already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 377
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: scrap_miner already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 523
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: angler already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 625
[17:11:08][game_singleobjectdatabase.h:165]: Object with key: puddle_technician already exists, using the one at  file: common/pop_jobs/23_agrarian_idyll_lithoid_worker_job_overrides.txt line: 724
[17:11:14][game_singleobjectdatabase.h:165]: Object with key: civic_agrarian_idyll already exists, using the one at  file: common/governments/civics/10_agrarian_idyll_lithoid_civic_overrides.txt line: 3
[17:11:14][game_singleobjectdatabase.h:165]: Object with key: civic_corporate_anglers already exists, using the one at  file: common/governments/civics/13_agrarian_idyll_lithoid_corporate_civic_overrides.txt line: 2
```

Normally overriding a single technology can cause problems with the game being confused by duplicates, but only technologies that are considered prerequisites for other technologies are affected. 

## Change Log

* 1.0.0 Initial version
* 1.1.0 Added missing compatibility notes, added Agrarian Idyll amenities to special event jobs
    * `titan_hunter` is in the `planet_farmers` resource category and already had code for amenities-related weighting for Agrarian Idyll, but lacked the actual amenities production for Agrarian Idyll (non-lithoid)
    * `cave_cleaner` is in the `planet_miners` resource category so it made sense to also apply amenities to it
    * purposely did not add agrarian idyll code to the potentially other relevant special job `ratling_scavenger` because it isn't for default countries
* 1.2.0 Include technician fix from [Enslaved Technician Job Priority Fix](https://steamcommunity.com/sharedfiles/filedetails/?id=2484702578)
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
* 2.0.0 Updated for Stellaris version 3.1.1 "Lem" - no changes to what the mod does, just integrated the underlying game changes
    * Scrap miners (used by Origin: Shattered Ring) benefit from Lithorian Idyll
    * Turtle miners (from an event) benefit from both versions of Agrarian Idyll (produces food and minerals)
    * Fix localisation mistake for the updated Agrarian Idyll tooltip - it's still for farmers, I promise!
* 2.0.1 Add priority weightings for Agrarian/Lithorian Idyll based on Charismatic/Repugnant to Turtle Miner job
* 2.0.2 Fix gas extractors (from Feral Overload) improperly disallowing enslaved species
* 3.0.0 Update for Stellaris version 3.2.1 "Herbert" - integrate underlying changes from the base game in overridden files
* 3.0.1 Mark as compatible with Stellaris version 3.2.2 "Herbert" - the game patch had no script changes
* 3.1.0 Remove full-file Society technology overwrite - now much more compatible with other mods!
* 3.1.1 Don't restrict the ability to work the Angler job to Anglers empires (allows other empires to employ Anglers should they somehow get access to the job)
* 4.0.0 Update for Stellaris version 3.3 "Libra"
    * Jobs and districts are no longer full-file overwrites!
    * Only the relevant `planet_farmer` and `planet_miner` jobs are overridden (but not Angler since the Anglers civic cannot be combined with Agrarian/Lithorian Idyll)
    * All rural districts are still overridden in order to apply the +capacity/+building slot bonus to them, but now only the ringworld farming district is overridden instead of all of them
    * Integrate underlying changes from 3.3 to overridden content
* 4.0.1 Jobs `crystal_miner`, `gas_extractor`, `mote_harvester` are now part of the `planet_sr_miners` category, as intended by Paradox
* 5.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Account for subterranean empires
    * Fix bug that was likely causing 0 weight for the Agrarian and Lithorian Idyll special housing technologies
    * Integrate underlying changes from 3.4 to overridden content
* 5.1.0 Add effects and triggers to improve district swaps
* 6.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Add `angler` job override, because it can now produce amenities for non-lithoid Agrarian Idyll empires
    * Add `puddle_technician` job override, because it can now produce amenities for non-lithoid Agrarian Idyll empires
    * Add `manufactorium_scraper` job override, so it can now produce amenities for lithoid Agrarian Idyll empires
    * Update override for Civic: Agrarian Idyll to support Civic: Anglers but deny Civic: Relentless Industrialists
    * Add override for Civic: Anglers (megacorp version only) to correctly allow it alongside Civic: Agrarian Idyll
    * No longers swap initial farming to mining districts for lithoids that are Anglers or Catalytic Processors
    * Remove extra carrying capacity from rural districts (it was overkill when combined with bonus housing)

## Source Code

Hosted on [Github](https://github.com/corsairmarks/agrarian_idyll_lithoid)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.