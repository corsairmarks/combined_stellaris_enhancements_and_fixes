# Overview

Adds an upgrade for Hydroponics Farm called Aquaponics Farms, which convert one farmer job into an Angler job.  The technology to construct this building is available to all non-gestalt empires.  Aquaponics is a combination of aquaculture (raising aquatic animals for food) where the nutrient-rich waste water is used to feed hydroponically-grown crops that filter it, and then re-used.  The new Angler job already represents aquaculture, so it felt appropriate to upgrade the Hydroponics Farm building to provide one of each job instead of farming only.

# Changes

Adds the new technology Aquaponics which creates an upgrade for the Hydroponics Farms called Aquaponics Farms.  Aquaponics Farms respect existing features of Hydroponics Farms: Void Dwellers gain an extra farmer job, Angler empires gain an extra Angler job on wet worlds, and farmer jobs convert to Acolytes of the Plow for Spiritualist fallen/awakened empires.

## Compatibility

Requires the Aquatics DLC.

Overwrites the built-in Hydroponics Farms building (`building_hydroponics_farm`) in order for it to be upgradeable to Aquaponics Farms.  Also overwrites the built-in Angler job (`angler`) so that any empire can work Angler jobs.

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

## Known Issues

Overriding a building, job, or trigger causes the game to log errors noting the overrides.  Expect to see five lines in the error.log file like these:

```
[20:27:45][game_singleobjectdatabase.h:165]: Object with key: building_hydroponics_farm already exists, using the one at  file: common/buildings/13_building_aquaponics_farm_resource_building_overrides.txt line: 6
[20:27:45][game_singleobjectdatabase.h:165]: Object with key: col_habitat_farming already exists, using the one at  file: common/colony_types/10_building_aquaponics_farm_colony_type_overrides.txt line: 3
[20:27:45][game_singleobjectdatabase.h:165]: Object with key: col_habitat_gestalt_farming already exists, using the one at  file: common/colony_types/10_building_aquaponics_farm_colony_type_overrides.txt line: 98
[20:27:47][game_singleobjectdatabase.h:165]: Object with key: has_any_farming_district_or_buildings already exists, using the one at  file: common/scripted_triggers/10_building_aquaponics_farm_scripted_trigger_overrides.txt line: 3
[20:27:49][game_singleobjectdatabase.h:165]: Object with key: angler already exists, using the one at  file: common/pop_jobs/13_building_aquaponics_farm_worker_job_overrides.txt line: 8
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Update name to be plural
* 1.0.2 Add override for the trigger `has_any_farming_district_or_buildings`, which helps the AI not get stuck in loops of creating/demolishing Food Processing buildings
* 2.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Use memory optimization feature for a trigger
    * Update `angler` job with changes from base game
* 3.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Remove defunct trigger reference to `buildings_simple_allow`
    * Update `angler` job with changes from base game, also account for "Agrarian" Idyll for Lithoids if installed
    * Hydroponics Farms or Aquaponics Farms on flooded habitats produce angler jobs in the same fashion as ocean worlds for angler empires
    * Add Aquaponics Farms build speed to `col_habitat_farming` (and the gestalt version)
    * You are more likely to draw Aquaponics technologies if you have the Javorian Pox Sample (same as Hydroponics)
* 3.1.0 Enable Aquaponics Farms for gestalt empires - they could already research the technology, but got nothing!
    * Add gestalt Aquaculture Drone (food and energy or amenities; machines get energy, hives and rogue servitors get amenities instead)
    * Update `angler` override to account for changes in another one of my mods

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/building_aquaponics_farm)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.