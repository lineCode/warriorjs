---
id: space-maker-api
title: Space API
---

You can call the same
[methods a player can call on a space](space-player-api.md), with only one
difference:

## `space.getUnit()`

Unlike the same method of the Player API, the unit returned by this method has
the full Unit API available.

**Returns**

_(Unit)_: The unit at this location.
