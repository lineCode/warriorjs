---
id: unit-maker-api
title: Unit API
---

You can call the same [methods a player can call on a unit](unit-player-api.md),
with the following additions:

## `unit.isAlive()`

Checks if the unit is alive.

A unit is alive if it has a position.

**Returns**

_(boolean)_: Whether the unit is alive or not.

## `unit.heal(amount)`

Adds the given amount of health in HP.

Health can't go over max health.

**Arguments**

`amount` _(number)_: The amount of HP to add.

## `unit.takeDamage(amount)`

Subtracts the given amount of health in HP.

If the unit is bound, it will unbound when taking damage.

Health can't go under zero. If it reaches zero, the unit will die and disappear
from the floor.

**Arguments**

`amount` _(number)_: The amount of HP to subtract.

## `unit.damage(receiver, amount)`

Damages another unit.

If the other unit dies, the unit that inflicted the damage will earn or lose
points depending on whether the killed unit was hostile (earn) or friendly
(lose).

**Arguments**

`receiver` _(Unit)_: The unit to damage.

`amount` _(number)_: The amount of HP to inflict.

## `unit.triggerEffect(effect)`

Triggers the given effect.

**Arguments**

`effect` _(string)_: The name of the effect.

## `unit.unbind()`

Unbinds the unit.

## `unit.bind()`

Binds the unit.

## `unit.earnPoints(points)`

Adds the given points to the score.

**Arguments**

`points` _(number)_: The points to earn.

## `unit.losePoints(points)`

Subtracts the given points from the score.

**Arguments**

`points` _(number)_: The points to lose.

## `unit.getOtherUnits()`

Returns the units in the floor minus this unit.

**Returns**

_(Unit[])_: The other units in the floor.

## `unit.getSpace()`

Returns the space where this unit is located.

**Returns**

_(Space)_: The space this unit is located at.

## `unit.getSpaceAt(direction, forward = 1, right = 0)`

Returns the space located at the direction and number of spaces.

**Arguments**

`direction` _(string)_: The direction.

`forward` _(number)_: The number of spaces forward.

`right` _(number)_: The number of spaces to the right.

**Returns**

_(Space)_: The space.

## `unit.getDirectionOfStairs()`

Returns the direction of the stairs with reference to this unit.

**Returns**

_(string)_: The relative direction of the stairs.

## `unit.getDirectionOf(space)`

Returns the direction of the given space with reference to this unit.

**Arguments**

`space` _(Space)_: The space to get the direction of.

**Returns**

_(string)_: The relative direction of the space.

## `unit.getDistanceOf(space)`

Returns the distance between the given space and this unit.

**Arguments**

`space` _(Space)_: The space to calculate the distance of.

**Returns**

_(number)_: The distance of the space.

## `unit.move(direction, forward = 1, right = 0)`

Moves the unit in the given direction and number of spaces.

**Arguments**

`direction` _(string)_: The direction.

`forward` _(number)_: The number of spaces forward.

`right` _(number)_: The number of spaces to the right.

## `unit.rotate(direction)`

Rotates the unit in a given direction.

**Arguments**

`direction` _(string)_: The direction in which to rotate.

## `unit.vanish()`

Vanishes the unit from the floor.

## `unit.say(message)`

Logs a message to the play log with the accompanying unit.

**Arguments**

`message` _(string)_: The message to log.

---

## Instance Properties

### `name` _(string)_

The name of the unit.

### `character` _(string)_

The character that represents the unit in the floor map.

### `health` _(number)_

The total damage the unit may take before dying, measured in Health Points (HP).

### `maxHealth` _(number)_

The starting `health` value.

### `score` _(number)_

The number of points earned by the unit.

### `reward` _(number)_

The number of points to reward when killed or released.

### `hostile` _(boolean)_

Whether the unit is hostile or not.

### `bound` _(boolean)_

Whether the unit is bound or not.
