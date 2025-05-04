# Full Code

Here's the full code for our basic example.

```py
import spawnbox

sbox = spawnbox.SpawnBox("My Title", 800, 600, (0, 0, 0, 255))

obj = spawnbox.Entity(sbox, 20, 20, 0, 0, (255, 255, 255))

@sbox.addUpdater
def update(delta):
    if sbox.input.pressed[sbox.input.keys["D"]]: # Right
        obj.x += 100 * delta
    elif sbox.input.pressed[sbox.input.keys["A"]]: # Left
        obj.x -= 100 * delta

@sbox.addDrawer
def draw():
    obj.draw()

sbox.mainloop()
```