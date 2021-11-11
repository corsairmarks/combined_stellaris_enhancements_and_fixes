# Overview

After a few requests for a small-resolution compatible "more districts" view, I decided to make this mod as an optional companion for [More Standard Districts](https://steamcommunity.com/sharedfiles/filedetails/?id=2650611194).  This mod is a very minor alteration to the built-in planetview screen, with the goal of maintaining the size of the planetview window in order to work with smaller-resolution screens (commonly 1366 and 1600 pixels wide).  Based on the changes made by Orrie for [Bigger Planet View](https://steamcommunity.com/sharedfiles/filedetails/?id=1587178040) (used with explicit permission).

# Changes

Alters the built-in planetview to have districts and buildings stacked vertically instead of horizontally, in order to accommodate a scrollbar for districts.

## Compatibility

Built for Stellaris version 3.1.\* "Lem."  As a UI-only mod, this is achievement compatible.  Not compatible with other mods that alter the planetview (`interface/`); does not alter the gamepad-based planetview.

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/basic-more-districts-planetview)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.