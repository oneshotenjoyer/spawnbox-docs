# Making a project.

To make a project, first open your code editor of choice (I, modguy07, choose to use Visual Studio Code for anything non-java, but you can use whatever you wish to use), and create a new python file. Start it with:

```py
import spawnbox
```

to import the SpawnBox library.

Then, create a SpawnBox object.
```py
sbox = spawnbox.SpawnBox("My Title", 800, 600, (0, 0, 0, 255))
# The arguments to the SpawnBox object are:
# title, width, height, background color.
# The background color is a RGBA tuple. (red, green, blue, transparency)
```

Then, create the update() and draw() functions, with the proper decorators, like so:
```py
@sbox.addUpdater
def update(delta):
    pass # We will write code here later.

@sbox.addDrawer
def draw():
    pass # We will write code here later.
```

And finally, we can make a window by ending the file with:

```py
sbox.mainloop()
```

Congratz! You have now created a window using SpawnBox. But it doesn't do much. Let's fix that.