# Overview

Like the idea of enlightened authoritarian rulers with Civic: Philosopher King but feel a bit underwhelmed at its actual affects?  Then this mod is for you!  It lightly enhances Civic: Philosopher King to have effects similar to those added to Civic: Distinguished Admiralty in Stellaris version 3.3 "Libra:" Governors begin with +2 levels.  Your initial ruler also begins at +2 levels, regardless of their leader class.

# Changes

Adds three events that grant bonus levels to Governors for empires with Civic: Philosopher King.  Overwrites the built-in Civic: Philosopher King to add localisation describing this effect.

## Compatibility

Any mod that does not remove Civic: Philosopher King.

Built for Stellaris version 3.8 "Gemini."  Not compatible with achievements.

### When to Install

This mod can be safely added or removed from your savegame after the game has started.  It is implemented entirely through custom events.  If you remove it, your game will work normally.  Any governors will keep their bonus levels.

### Recommended Companion Mods

* [Civic: Organic Zealots](https://steamcommunity.com/sharedfiles/filedetails/?id=2920668465) adds a brand-new civic - play as a homicidal empire determined to eliminate artificial intelligence
* [Civic: Byzantine Bureaucracy - Enhanced](https://steamcommunity.com/sharedfiles/filedetails/?id=2774084358) enhances Civic: Byzantine Bureaucracy to add bonus amenities to Bureaucrats and also add a new ruler-stratum job, the Magistrate
* [Origin: Jovian League](https://steamcommunity.com/sharedfiles/filedetails/?id=2682659676) adds a brand-new origin that allows almost any empire to begin spanning four small colonies on the moons of a gas giant rather than they typical large, single planet

## Localisation

The text describing the effects for Civic: Philosopher King has been edited to describe its new effect for eight officially-supported Stellaris languages.  I'm reasonably confident in my splicing for most languages, although I may have used the wrong word for "and" in Chinese.  It is not translated for Korean or Japanese.

## Known Issues

Overriding many types of game objects causes the game to log errors noting each override. Expect to see one line in the error.log file like this:

```
[05:45:57][game_singleobjectdatabase.h:153]: Object with key: civic_philosopher_king already exists, using the one at  file: common/governments/civics/10_civic_philosopher_king_enhanced_civic_overrides.txt line: 2
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Remove mod flag - as a small rules change, having a detection flag seems extraneous
* 1.0.2 Fix localisation for Chinese and Spanish - the files accidentally claimed to be English!
* 1.1.0 Flagged as compatible with Stellaris version 3.4 "Cepheus" - no actual changes
* 1.2.0 Flagged as compatible with Stellaris version 3.6 "Orion" - no actual changes
* 1.3.0 Add a compatibility trigger for other mods to check whether this one is active
* 1.4.0 Flagged as compatible with Stellaris version 3.7 "Canis Minor" - no actual changes
* 2.0.0 Update for Stellaris version 3.8 "Gemini"
    * Add override of Civic: Philosopher King to ensure the effect tooltip is displayed
    * Remove references to the "ruler" leader class in the description - it no longer exists
    * Empires which begin the game with Civic: Philosopher King receive +2 levels to their initial ruler, regardless of leader class
* 2.1.0 Adjust how leader levels are added for Civic: Philosopher King - leaders that are already owned allow for the selection of their traits (similar to Civic: Distinguished Admiralty)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/civic_philosopher_king_enhanced)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.