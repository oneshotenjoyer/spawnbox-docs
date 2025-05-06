# spawnbox.Entity()

Parameters:

```py
spawnbox.Entity(window: SpawnBox, width = 20, height = 20, x = 0, y = 0, color = (255, 255, 255, 255))

# If a parameter looks like:
# <name> = <value>,
# then <value> is the default value.
# e.g, height = 20 - the default height is 20.
```
<hr />
Functions:

<br />

`draw()` - Draws it to the screen at the current X and Y.

`collide(entity)` - Checks if the current entity is colliding with the specified entity.

`center()` - Moves entity to the center of the screen.

`center_x()` - Moves the entity to the center, but only on the X axis.

`center_y()` - Moves the entity to the center, but only on the Y axis.

`distance(entity, other entity)` - Calculates the distance between 2 entities (in pixels)