# Overview

Have you ever conquered a Machine World as a regular empire?  Or perhaps you ended up with one after integrating a machine subject?  The build-in Replicator job is not usable by regular empires - so this mod set out to fix that.

However, instead of just adding a Roboticist job and calling it a day, I decided to add a little extra flavor.  Machine Worlds themselves are gestalt consciousnesses even when disconnected from a Machine Intelligence.  While content to continue their existence without expanding, they will only grant their production bonuses (and a Roboticist job) to empires that enfranchise AI.  Conversely, empires that ban AI will have their efforts to use the Machine World subtly hampered by the world itself, in the form of additional penalties.  They are watching your policy decisions and will adjust their opinion of you accordingly.

# Changes

Machine Worlds owned by regular empires now have a planetary modifier (visible on the planet view) that displays the Machine World's opinion of your empire (Cooperative, Neutral, or Hostile).  All levels remove the built-in Replicator job, but the top level (Cooperative) grants a Roboticist job to replace it.  Neutral opinion cancels out the inherent Machine World production bonuses, and Hostile cancels out the bonuses and adds additional production and maintenance penalties.

## Compatibility

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

Because the extra Roboticist job is added via a planetary modifier, that means it was **not** necessary to overwrite planet classes - opening up compatibility with many other mods that do make planet class changes.  However, the built-in Machine World starting deposit `d_resource_consolidation_1` (Malfunctioning Replicator Bay) was overwritten to block the Roboticist job granted by the custom modifier.

This mod also overwrites the `district_industrial` in order to properly shift jobs to and from Metallurgists and Artisans based on Machine World colony designations, and overwrites the `col_mac_factory` (Machine World Factory) colony designation in order to account for the 3rd-tier factory building.  What this means to you is that this mod is not compatible with other mods that alter industrial districts or (much more unlikely) the Machine World Factory colony designation.

### Recommended Companion Mods

* [Deassimilate Machines](https://steamcommunity.com/sharedfiles/filedetails/?id=2553812372) allows you to deassimilate machine Pops into Robots, and is the original inspiration for Deassimilated Machine Worlds.
* [Retain Leaders from Integrated Subjects](https://steamcommunity.com/sharedfiles/filedetails/?id=2553818684) will allow you to keep Machine Unit leaders from integrated machine empire subjects by converting them to robots and setting their species to deassimilation.  Combined with Leader Traits: All Eligible Species Traits, the leaders are converted to have synth leader traits if you have the right technology.

Together with the above two mods, you're more likely to obtain a Machine World as a non-Machine empire.

### When to Install

This mod can be safely added to your savegame after the game has started.  Because it adds static modifiers for planets, it is not advisable to remove during gameplay.  If removed, you will lose access to the special Machine World modifiers and events - Stellaris is usually fairly forgiving and just removes missing modifiers, but it has not been explicitly tested.  Back up your savegame before trying to remove a mod.

## Known Issues

Overriding the district, colony designation, and deposit causes the game to log three errors like this:

```
[15:22:33][game_singleobjectdatabase.h:165]: Object with key: district_industrial already exists, using the one at  file: common/districts/10_deassimilated_machine_worlds_urban_district_overrides.txt line: 4
[15:22:34][game_singleobjectdatabase.h:165]: Object with key: col_mac_factory already exists, using the one at  file: common/colony_types/01_deassimilated_machine_world_override_colony_types.txt line: 6
[15:22:35][game_singleobjectdatabase.h:165]: Object with key: d_resource_consolidation_1 already exists, using the one at  file: common/deposits/08_deassimilated_machine_worlds_federations_deposits_overrides.txt line: 1
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Bugfixes
    * Prevent confusing initial event description complaining about lack of synth rights when the empire does in fact have synth rights
    * Machine empires won't get a Machine World opinion because they integrate it (debuffs suck)
    * Don't add duplicate modifiers to Machine Worlds
* 2.0.0 Update for Stellaris version 3.1 "Lem"
    * Update district overrides to import new features, such as the special new artificer and catalytic technician jobs
    * Update `col_mac_factory` override
    * Add Malfunctioning Replicator Bay blocker override to also block the free Roboticist job
* 2.1.0 Update for Stellaris version 3.2 "Herbert" - no changes (yes it surprised me too)
* 3.0.0 Update for Stellaris version 3.3 "Libra"
    * Districts are no longer full-file overwrites!
    * Only the relevant `district_industrial` district is overridden
    * Integrate additional changes from 3.3 to overridden content
* 4.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Use memory optimization feature for effects and triggers
    * Update overridden Machine World Factory to account for sector automation
    * Neutral and Hostile Machine Worlds negate the resettlement bonus chance (which was added to Machine Worlds in 3.4)
* 5.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Adjust Industrial District job tooltips to appear only when the relevant job swaps are activated, using the triggers provided by PDS (not sure why they did not use these triggers their changes)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/deassimilated_machine_worlds)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.