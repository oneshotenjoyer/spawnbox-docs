# spawnbox.SpawnBox()

Parameters:

```py
spawnbox.SpawnBox("title", width, height, background color)

# The background color must be an RGBA tuple.
# e.g, (0, 0, 0, 255)
#      (R, G, B, TRANSPARENCY)
```
<hr />
Functions:

`mainloop()` - Runs the project. Must be called from an initialized `SpawnBox` object.
`quit()` - Stops the current project's execution. Must be called from an initialized `SpawnBox` object.

<hr />
Decorators:

`@addUpdater` - The function this decorater is attatched to becomes an update function. Runs once per frame. Supplies `delta` (delta time).

`@addDrawer` - The function this decorater is attatched to becomes a draw function. Runs once per frame.

`@init` - The function this decorator is attatched to becomes *the* init function. Runs once before the project starts. There can only be one init function.