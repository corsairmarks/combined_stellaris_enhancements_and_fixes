# Overview

Summary

# Changes

Notes

## Compatibility

Notes

## Known Issues

```
[14:12:47][game_singleobjectdatabase.h:147]: Object with key: building_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 10
[14:12:47][game_singleobjectdatabase.h:147]: Object with key: building_major_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 293
[14:12:47][game_singleobjectdatabase.h:147]: Object with key: building_system_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 587
[14:12:47][game_singleobjectdatabase.h:147]: Object with key: building_hab_major_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 898
[14:12:47][game_singleobjectdatabase.h:147]: Object with key: building_imperial_capital already exists, using the one at  file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1255
[14:12:58][trigger_impl.cpp:3320]: Error in has_designation/colony_type trigger, cannot find planet designation with key: col_srw_trade file: in scripted trigger should_swap_extra_merchants at file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1168 line: 1
[14:12:58][trigger_impl.cpp:3320]: Error in has_designation/colony_type trigger, cannot find planet designation with key: col_ecu_trade file: in scripted trigger should_swap_extra_merchants at file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1168 line: 1
[14:12:59][trigger_impl.cpp:3320]: Error in has_designation/colony_type trigger, cannot find planet designation with key: col_srw_trade file: in scripted trigger should_swap_extra_merchants at file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1168 line: 1
[14:12:59][trigger_impl.cpp:3320]: Error in has_designation/colony_type trigger, cannot find planet designation with key: col_ecu_trade file: in scripted trigger should_swap_extra_merchants at file: common/buildings/10_building_capital_colony_type_job_swaps_capital_building_overrides.txt line: 1168 line: 1
```

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub]()

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.