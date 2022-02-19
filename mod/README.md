# Overview

Adds an upgrade for Hydroponics Farm called the Aquaponics Farm, which converts one farmer job into an Angler job.  The technology to construct this building is available to all non-gestalt empires.  Aquaponics is a combination of aquaculture (raising aquatic animals for food) where the nutrient-rich waste water is used to feed hydroponically-grown crops that filter it, and then re-used.  The new Angler job already represents aquaculture, so it felt appropriate to upgrade the Hydroponics Farm building to provide one of each job instead of farming only.

# Changes

Adds the new technology Aquaponics which creates an upgrade for the Hydroponics Farms called an Aquaponics Farm.  The Aquaponics Farm respects existing features of the Hydroponics Farm: Void Dwellers gain an extra farmer job, Angler empires gain an extra Angler job on wet worlds, and farmer jobs convert to Acolytes of the Plow for Spiritualist fallen/awakened empires.

## Compatibility

Requires the Aquatics DLC.

Overwrites the built-in Hydroponics Farm building (`building_hydroponics_farm`) in order for it to be upgradeable to an Aquaponics Farm.  Also overwrites the built-in Angler job (`angler`) so that any empire can work Angler jobs.

## Known Issues

Overriding a building or job causes the game to log errors noting the overrides.  Expect to see two lines in the error.log file like these:

```
[01:53:56][game_singleobjectdatabase.h:147]: Object with key: angler already exists, using the one at  file: common/pop_jobs/13_building_aquaponics_farm_worker_job_overrides.txt line: 7
[01:54:03][game_singleobjectdatabase.h:147]: Object with key: building_hydroponics_farm already exists, using the one at  file: common/buildings/13_building_aquaponics_farm_resource_building_overrides.txt line: 6
```

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/building_aquaponics_farm)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.