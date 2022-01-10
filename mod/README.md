# Overview

After a few requests for a low-resolution compatible "more districts" view, I decided to make this mod as an optional companion for [More Standard Districts](https://steamcommunity.com/sharedfiles/filedetails/?id=2650611194).  This mod is a very minor alteration to the built-in planetview screen, with the goal of retaining the default size of the planetview window in order to work with lower-resolution screens (commonly 1366 and 1600 pixels wide).  Based in part on changes made by Orrie for [Bigger Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1587178040) (used with explicit permission).

Credit for my motivation goes to arievilo and Kyllian.

# Changes

Alters the built-in planetview to have districts and buildings stacked vertically instead of horizontally, in order to accommodate a scrollbar for districts.  Up to 12 kinds of districts can be displayed.  This mod does _not_ add any additional building slots.

## Compatibility

Built for Stellaris version 3.2.\* "Herbert," backwards compatible with version 3.1.\* "Lem."  As a UI-only mod, this is achievement compatible.  Not compatible with other mods that alter the planetview (`interface/planet_view.gui`); does not alter the gamepad-based planetview.  In particular, this mod is incompatible with many UI overhaul mods and any mod that adds more building slots because they will all be in contention to modify the same file.

### Recommended Companion Mods

[More Standard Districts](https://steamcommunity.com/sharedfiles/filedetails/?id=2650611194) adds 5 district types based on basic buildings: Research, Commercial, Leisure, Military, and Administrative.  Commercial Districts are not available for gestalt empires and Leisure Districts are only available for regular empires and Rogue Servitors.

[Basic Planetview: More Districts & Buildings](url=https://steamcommunity.com/sharedfiles/filedetails/?id=2714695762) adds 3 additional building slots for use with this mod.  Number of additional districts limited by lack of scrollbars for this part of the UI.

### Not Included in "Subtle Polish"

This mod is intentionally not included in my modpack [Subtle Polish: A Collection of Fixes and Enhancements](https://steamcommunity.com/sharedfiles/filedetails/?id=2522974089) because it is an optional, basic UI change targeted at specific screen resolutions.

## Changelog

* 1.0.0 Initial version
* 1.1.0 Mark as compatible with Stellaris version 3.2 "Herbert"
* 1.2.0 Add support for 5 rows of building slots - enabling it requires the submod [Basic Planetview: More Districts & Buildings](url=https://steamcommunity.com/sharedfiles/filedetails/?id=2714695762)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/basic-more-districts-planetview)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.