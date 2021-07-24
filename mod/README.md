# Overview

Have you ever wanted to entrust your Battle Thralls to lead on the battlefield? With this mod you now have the option to allow your Battle Thralls greater freedom to command ships and armies as Admirals and Generals.

In addition to just Battle Thralls being eligible to be rolled as military leaders, any species with Full Military Service can be rewarded as a promoted captain after destroying an enemy fleet.  The free admiral from a promotion is built in, but by default it only ever rewards admirals of the owner's main species.

# Changes

The Battle Thralls slavery type is allowed to be assigned the Full Military Service service type, which then allows them to become military leaders - Admirals and Generals.  In order to achieve this, I've attached an event to `on_leader_spawned` that can alter the species of the spawned leader to any species which has Full Military Service; this applies anywhere leaders are created.  The leader's species is randomly rerolled by seelcting a Pop out of all those that have Full Military service and using that species, and is thus implicilty weighted based on the relative population size of the eligible species.  Second, I've updated Full Military Service to be selectable for Battle Thralls.  As a bonus for allowing Battle Thralls even greater responsibility, their Pops are 10% happier when given Full Military Service.

In addition to allowing Battle Thralls to have Full Military Service, I slightly updated the conditions for which it is allowed.  Necrophages now cannot set any species that is not their main necrophage species to have Full Military Service (as described in the origin) and the allowing Full Military Service for robots now requires Synthetic Personality Matrix rather than Droids.  Syncretic Proles (as described by the trait) and nonsentients cannot be military leaders.  Hive and Machine empires are unaffected by these changes.

As a minor quality-of-life enhancement, I have also attached an event to `on_fleet_destroyed_perp` that will fire after `leader.1` (captain promoted to admiral) has generated a leader of the owner's main species.  This allows the species of that leader to be rerolled if the empire in question allows Full Military Service for any non-main, non-Battle Thrall species.  If there is a species of Battle Thralls with Full Military Service, then the leader has already had a shot at having their species rerolled.

Finally, because this mod was inspired by my role-play for the [Eldanær Stellar Authority](https://steamcommunity.com/sharedfiles/filedetails/?id=2496360535) it also allows bypassing the xenophobic and necrophage restrictions for allowing Full Military Service.  You can bypass these restrictions by using the custom Edict called "Decree: Honored Protectors" which will let you choose from any species that you have set to Citizenship: Slavery and Slavery Type: Battle Thralls for 100 influence.  The chosen species has a flag applied (previously two flags) and is set to Military Service: Full Military Service.

This mod is set to detect any species previously flagged in a single player game, and attempt to convert the old flags into the new (country-specific) flag.  It things still don't work right (or you were in a multiplayer game) then you can either use the edict to apply the flag, or use the console to execute an effect to manually add the flag.

### When to Install

This mod can be safely added to your savegame after the game has started, but not removed.  Because this mod alters the game rules, removing it could result in problems as the game detects a now-ivalid citizenship/military service combination - or it might just force your Battle Thralls out of military full service.  If you'd like to find out, make a backup of your savegame before experimenting.

# Recommended Companion Mods

If you like species traits that add leader traits, check out my mod [Leader Traits: All Eligible Species Traits](https://steamcommunity.com/sharedfiles/filedetails/?id=2499031295).  It is fully compatible with this mod.  The most notable interaction occurs when your Battle Thrall species is chosen for becoming a random admiral after destroying an enemy fleet - with this mod your promoted captains will properly gain their species traits.

## Compatibility

Because this mod replaces two built-in objects, it is inherently incompatible with mods that alter the same objects.  While I doubt most mods will fiddle with `can_be_military_leader` it is likely any mods that are altering citizenship, military service, and/or slavery type could overlap with this one.  The only species right that this mod overrides is `military_service_full`.

This mod is specifically engineered to be compatible with my other mod that affects military service: [Deassimiliate Machines](https://steamcommunity.com/sharedfiles/filedetails/?id=2553812372).

This mod is not compatible with achievements.

## Localisation

This mod is mostly localized for every language supported by Stellaris - mainly because it uses the built-in localisation.

The updated Full Military Service species right now enforces that necrophage empires cannot select it for non-main species and needed a tooltip.  I created this tooltip by taking the first half of the second bullet point from the built-in localisation for the necrophage origin's effects, `civic_tooltip_necrophage_effects` in the file `localisation/<language>/necroids_l_<language>.yml`.  In English that is "Only Necrophage Pops may be leaders."  If I have destroyed your language and you'd like to suggest a better translation, please leave a comment or message me.

I also found that the built-in localisation for `any_galaxy_species_trigger` was incorrect and referred to a "Number of Species in the Galaxy" when instead it should say "Any Species in the Galaxy" (English).  I've attempted some tooltip splicing to get the right translations for other languages (except Simplified Chinese).  As above, please comment or message me if I have massacred your language and you would like to help.

However, the new edict to declare Battle Thralls as Honored Protectors is not localised - that is because it is my original writing.  The english text is used as a placeholder for other languages.  If you want to translate it into your language, please leave a comment or message me.

## Known Issues

This mode overrides a built-in trigger `can_be_military_leader` and a species right `military_service_full`.  These overrides each cause the game to log an error, so expect to see two lines in error.log like this:

```
[20:51:18][game_singleobjectdatabase.h:147]: Object with key: can_be_military_leader already exists
[20:51:20][game_singleobjectdatabase.h:147]: Object with key: military_service_full already exists
```

## Change Log

* 1.0.0 Initial version
* 1.1.0 Add event to flag mod as installed
* 1.1.1 Remove extra images files to keep distribution lightweight (no script changes)
* 1.2.0 remove monthly pulse for mod flag
* 1.3.0 Enhance compatibility with [Gender Nonbinary Leaders](https://steamcommunity.com/sharedfiles/filedetails/?id=2528614880)
* 1.4.0 Enhance compatibility with my other mods that work with changing leader species - no gameplay changes in this mod
* 1.5.0 Add edict "Decree: Honored Protectors" so players can choose Battle Thralls they'd like to allow Full Military Service, despite being xenophobic and/or a necrophage
* 1.5.1 Add test event

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/battle_thrall_military_leaders)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.
