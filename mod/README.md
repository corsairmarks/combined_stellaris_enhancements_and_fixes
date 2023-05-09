# Overview

Do you have trouble finding your "in-progress" terraforming planets?  Or maybe you miss terraform stations?  This mod is for you!  The new terraforming gameplay is a bit less clunky to use, but does suffer from a lack of visual pizzazz.  This mod reintroduces terraform stations, and the best part is that you don't have to do anything special, use resources, or pay maintenance!

When a planet begins terraforming, this mod will automatically spawn a terraform station above it complete with sound effects, an animated terraform beam, and a healthy green glow around the planet.  These stations are real gameplay objects, but losing (or disbanding) them does not affect the terraforming process - it is purely a visual embellishment.  Once terraforming completes, your geo-engineers will automatically dismantle the terraform station.  If you cancel terraforming, expect a delay of up to one month (30 days) before the station will be automatically decommissioned.

## Recommend a Shipset

Would you like this mod to offer a sub-mod for your favourite shipset?  Please ask nicely and provide a link to the shipset you'd like to have matching terraform stations.  For compatibility, I'll use the terraform station graphics if the shipset has a unique model, or whatever model is defined for the terraform station in the mod's entities.  Finally, I'll fall back to picking the same model as the mining station, research station, or possibly outpost (if there are not custom graphics for the mining/research stations).

# Changes

Reintroduces terraform stations and existing (but unused) graphical effects to provide a more obvious indicator when planets are terraforming.  Events attached to the `on_terraforming_begun` and `on_terraforming_complete` provide the basic functionality.  However, there is no on_action for when terraforming is cancelled - instead, each station checks monthly whether the planet below is still terraforming - if not, it decommissions itself.

## Compatibility

This mod reuses existing game entities and 3D assets plus new events to handle the spawning and despawning for terraform stations.  The terraform station ship size is restored to the game and used to create real stations as visual markers.  What this means to you is that this mod should work with practically any other mod, although new shipsets will use their fallback option for terraform stations.

Built for Stellaris version 3.7 "Canis Minor."  Not compatible with achievements.

### When to Install

This mod should be added before you start a new game so that all empires are assigned a (hidden) ship design for terraform stations.  Without the design, there is no way to spawn the terraform station fleets.  Furthermore, this mod should not be removed from a game in-progress.  Losing access to the ship size or entities may cause issues if there are any terraform stations still active, and attempting to fire an event that doesn't exist will frequently result in a crash.

### Recommended Companion Mods

* [Aesthetic Terraform Stations (collection)](https://steamcommunity.com/sharedfiles/filedetails/?id=2667853075) is a list of all supported shipsets and their corresponding Aesthetic Terraform Station compatibility sub-mods
* [Ringworld Graphical Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2628518102) or [Subtle Polish: A Collection of Fixes and Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2522974089) to set your Origin: Shattered Ring empires to have ringworlds matching their shipset (graphical culture)
* [Machine Shipset](https://steamcommunity.com/sharedfiles/filedetails/?id=2077186491) is a phenomenal, fully-sectioned shipset and includes megastructures
* [Machine Shipset Add-on: Shattered Ring and Habitat Appearance](https://steamcommunity.com/sharedfiles/filedetails/?id=2628980994) ensures that the permanently-destroyed sections for Origin: Shattered Ring using the Machine Shipset properly display as that shipset (adds missing graphical definitions to the Machine Shipset and enhances the appearance of its habitable ringworlds segments and mini-ring habitats)

## Known Issues

The terraform station "beam" is a fixed length and may not reach down to small planet, or might become buried beneath the crust of larger planets.  There is not a good way to dynamically scale the entity inversely to planet size with script, so an arbitrary length was chosen.

## Changelog

* 1.0.0 Initial version
* 1.0.1 Decrease overlap in effects when installed with ["Terraform" to Tomb World](https://steamcommunity.com/sharedfiles/filedetails/?id=2625663437)
* 2.0.0 Upgrade for compatibility with Stellaris version 3.2 "Herbert"
    * Account for new radiotrophic variant
    * Verify the fallback is used for Aquatic
* 2.1.0 Mark as compatible with Stellaris version 3.3 "Libra"
    * Improve trigger for determining if a species is "nuked" - this change is a general upgrade, not specific to version 3.3 "Libra"
* 3.0.0 Upgrade for compatibility with Stellaris version 3.4 "Cepheus"
* 4.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Account for new radiotrophic variants (matters only when used alongside ["Terraform" to Tomb World](https://steamcommunity.com/sharedfiles/filedetails/?id=2625663437))
    * Toxoid shipset does not have a unique Terraform Station, so it should use the appropriate fallback (Mammalian)
* 4.0.1 Remove duplicate property from the megastructure variation (code cleanup)
* 5.0.0 Compatibility triggers
    * Add a compatibility trigger for other mods to check whether this one is active
    * Consume the compatibility trigger from another mod
    * Remove old compatibility global flag
* 5.1.0 Mark as compatible with Stellaris version 3.7 "Canis Minor"
* 5.2.0 Minor enhancements to support more shipsets
    * Use the built-in `scripted_variable` for terraform station hit points
    * Use an empty named section entity (so sub-mods can choose to use two-part stations, such as the built-in `ai_01` stations that rotate) rather than directly pointing to the empty section entity
* 5.3.0 Mark as compatible with Stellaris version 3.8 "Gemini" - no script changes

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/terraform_stations_aesthetic)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.