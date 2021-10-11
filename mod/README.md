# Overview

Do you have trouble finding you "in-progress" terraforming planets?  Or maybe you miss terraform stations?  This mod is for you!  The new terraforming gameplay is a bit less clunky to use, but does suffer from a lack of visual pizzazz.  This mod reintroduces terraform stations, and the best past is that you don't have to do anything special, use resources, or pay maintenance!

When a planet begins terraforming, this mod will automatically spawn a terraform station above it complete with sound effects, an animated terraform beam, and a healthy green glow around the planet.  These stations are real gameplay objects, but losing (or disbanding) them does not affect the terraforming process - it is purely a visual embellishment.  Once terraforming completes, your geo-engineers will automatically dismantle the terraform station.  If you cancel terraforming, expect a delay of up to one month (30 days) before the station will be automatically decommissioned.

# Changes

Reintroduces terraform stations and existing (but unused) graphical effects to provide a more obvious indicator when planets are terraforming.  Events attached to the `on_terraforming_begun` and `on_terraforming_complete` provide the basic functionality.  However, there is no on_action for when terraforming is cancelled - instead, each station checks monthly whether the planet below is still terraforming - if not, it decommissions itself.

## Compatibility

This mod reuses existing game entities and 3D assets plus new events to handle the spawning and despawning for terraform stations.  The terraform station ship size is restored to the game and used to create real stations as visual markers.  What this means to you is that this mod should work with practically any other mod, although new shipsets will use their fallback option for terraform stations.

Built for Stellaris version 3.1.\* "Lem."  Not compatible with achievements.

### When to Install

This mod should be added before you start a new game so that all empires are assigned a (hidden) ship design for terraform stations.  Without the design, there is no way to spawn the terraform station fleets.  Furthermore, this mod should not be removed from a game in-progress.  Losing access to the ship size or entities may cause issues if there are any terraform stations still active, and attempting to fire an event that doesn't exist will frequently result in a crash.

## Known Issues

The terraform station "beam" is a fixed length and may not reach down to small planet, or might become buried beneath the crust of larger planets.  There is not a good way to dynamically scale the entity inversely to planet size with script, so an arbitrary length was chosen.

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/terraform_stations_aesthetic)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.