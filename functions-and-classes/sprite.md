# spawnbox.Sprite()

Parameters:

```py
spawnbox.Sprite(window: SpawnBox, file, width = 200, height = 200, x = 0, y = 0)
```
<hr />
Functions:

This class retains multiple functions from [spawnbox.Entity()](entity.md), along with:

`add_animation(animation: spawnbox.ext.Animation, name: str)` - Adds an animation (a set of PNGs / JPGs) to the Sprite, that can be played.

`play_animation(name: str)` - Plays an animation added by add_animation().

`mirror_x()` - Mirrors on the X axis. Will override or be overridden by mirror_y().

`mirror_y()` - Mirrors on the Y axis. Will override or be overridden by mirror_x().

`mirror_default()` - Unmirrors on all axis.