# Make your first game
Now, we're going to create a simple Pong game using ```spawnbox```.

To start, create a new python file named ```pong.py```, and set it up with the following code:

```py
from spawnbox import *

sbox = SpawnBox("Pong", 800, 600, (0, 0, 0, 255))

@sbox.addUpdater
def update(delta):
    pass

@sbox.addDrawer
def draw():
    pass

@sbox.init
def init():
    pass
```

Now, you have a blank window titled "Pong". Now, let's start making our game.