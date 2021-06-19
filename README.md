# Primitive Conquest Enhancements

In default (unmodded) Stellaris, when a player conquers a primitive planet (or ringworld segment), he/she is given free districts based on the number
of Pops conquered.  The city districts are the wrong type for machine and hive empires, and players receive farming districts on worlds that previously
housed a lithoid primitive civilization.  The AI does not receive these bonus districts.

It's my opinion that these free districts represent repurposing existing infrastructure for the conqueror's use.  To that end, this mod gives the
proper type of city, nexus, or hive districts as appropriate for the conquering empire type.  Second, planets (or ringworld segments) inhabited by
lithoid civilizations receive mining districts (or extra ringworld housing) as opposed to farming districts/segments.  Rogue servitors get organic
sanctuaries instead of some of the nexus districts, because preserving some developed areas allows bio-trophies to live in their "natural habitat."
Finally, the AI benefits from these free districts in order to even the playing field.

## A Bit More Detail

This mod started as a response to four very specific, small areas:

1. When conquering primitive planets, human players get free districts to employ about half the population, but the AI does not
2. Machine Empires and Hive Empires were given city districts instead of the appropriate nexus or hive districts
3. When conquering a lithoid primitive planet, the player is given farming districts, which lithoids wouldn't need
4. Necrophage AI players have a special helper event to gain control of primitives, but it is not actually conquest and thus misses out on some things

To address these issues, this mod implements free districts upon conquering a primitive planet for both players and AIs.  It also generates the appropriate
housing/urban districts based on the conquering empire (including some organic sanctuaries for Rogue Servitors).  Mining districts are generated instead of
farming districts if the conquered primitive species is lithoid.  Finally, it triggers the aforementioned free district creation in the Necrophage AI helper
event.  In combination, these small changes should help AI players be a bit more successful when conquering primitive planets.

# Technical Changes

This mod replaces three events from the base game: `action.14`, `action.140`, and `necroids.6`.  Due to how events are loaded by Stellaris, the file
from this mod is named to load before the base game files.  Events with duplicate IDs generate entries in the error.log file (and the first one loaded
is used), so this mod is expected to generate three error lines that look similar to this:

```
# [01:07:25][eventmanager.cpp:355]: an event with id [necroids.6] already exists!  file: events/necroids_events_1.txt line: 518
# [01:07:25][eventmanager.cpp:355]: an event with id [action.14] already exists!  file: events/on_action_events.txt line: 5824
# [01:07:25][eventmanager.cpp:355]: an event with id [action.140] already exists!  file: events/on_action_events.txt line: 5886
```

# Compatibility

You do **not** need the Necroids or Lithoids content packs to use this mod.

This mod should be widely compatible with other mods.  Incompatibilities would only occur if other mods also overwrite the same event IDs.  If another mod is
attempting to make changes to primitive planet conquest but uses a different method (for example, adding new events activated by on action events such as
`on_planet_transfer`, `on_planet_conquer`, or `on_planet_attackers_win`) the end result could be extra districts or other nonsensical behavior after both mods
apply their effects.

This mod is not compatible with achievements because it overwrites data from core Stellaris files.

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add machine/hive empire support
* 1.2.0 Ringworld support (e.g. Sanctuary), add images and explanations
* 1.2.1 Flagged as compatible with Stellaris 3.0.* (no script changes)