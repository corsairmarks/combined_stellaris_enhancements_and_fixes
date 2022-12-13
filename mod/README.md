# Overview

Want to activate unity-based edicts right at game start?  With this mod, you can!  No more waiting a month to have a positive unity balance in order to start things like Information Quarantine or Peace Festivals.  Your empire will begin with a small amount of unity equal to your edicts fund, alloying you to enable edicts immediately.

Inspired by HFY in this [forum post](https://forum.paradoxplaza.com/forum/threads/3-3-libra-please-start-every-empire-with-some-unity-so-we-can-activate-edicts-on-day-1.1513564/).

# Changes

Adds one event that fires at game start.  This event calculates the value of each empire's unity fund based on leader skill, leader traits, and civics and then grants that amount of starting unity.

## Compatibility

Compatible with practically anything.  Limitations: this mod is hard-coded to understand the amount of edict fund given by built-in game effects only, because the modifier value does not seem eligible for export and use in script.  That means it will **not** account for custom traits/civics/etc that also add edict fund or changes to the amount of fund granted by the built-in effects.

Build for Stellaris version 3.6 "Orion."  Not compatible with achievements - however, you can start an Ironman game with this mod active, exit and disable the mod, and then resume your game.  That _should_ allow you to earn achievements, because the game doesn't seem to track whether mods have ever been active for a game, just if the checksum is modified when you earn the achievement.

## Changelog

* 1.0.0 Initial version
* 1.1.0 Flagged as compatible with Stellaris 3.4 "Cepheus" - no actual changes
* 2.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Account for edicts fund boosts for Civic: Efficient Bureaucracy from bureaucrats, priests, death priests, and managers (based on unity output)
    * Account for edicts fund boosts for authoritarian empires from culture workers and death chroniclers (based on level of authoritarianism)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/start_with_unity_fund)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.