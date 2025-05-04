# Adding Input

Now that we have a SpawnBox object, and knowledge on how entities work, let's handle input.

Input is already implemented in the SpawnBox object, so that's essentially handled already.

Now, let's use the implemented input object to move the character left and right.

Let's start by analyzing how input is handled.

```py
sbox.input.pressed[sbox.input.keys[key]]
# This looks convoluted, that's because it is.
# Keys include:
# Numbers, the alphabet keys, UP, DOWN, LEFT, RIGHT,
# F1-15, LALT, RALT, LSHIFT, RSHIFT, LCTRL, RCTRL,
# HOME, DELETE, INSERT, END, SPACE & PLUS.

# Because of how input.keys is implemented, key has to be the regular name for the key, in caps. Not including the number keys.

# e.g + = PLUS, a = A, 1 = 1.
```

So, now that we have that explanation out of the way, let's implement our movement.

```py
@sbox.addUpdater
def update(delta):
    if sbox.input.pressed[sbox.input.keys["D"]]: # Right
        entity.x += 100 * delta
    elif sbox.input.pressed[sbox.input.keys["A"]]: # Left
        entity.x -= 100 * delta
```

Now, test your project, and now you can move left and right with the D and A keys.

![A white box moving slowly across the top of the screen.](../img/moving.gif)

Now that we know how to move a box arround with the arrow keys, you can easily recreate most simple games like pong, space invaders, etc.
