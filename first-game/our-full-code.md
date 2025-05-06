# Our Full Code

Here's the full script for the Pong game.

```py
from spawnbox import *
import random

sbox = SpawnBox("Pong", 800, 600, (0, 0, 0, 255))

class Paddle(Entity):
    def __init__(self, x, y): # we can leave most of the parameters as their default values.
        super().__init__(sbox, 10, 100, x, y)
        self.ball = None # this will be used for the enemy
    
    def player_movement(self, delta):
        if sbox.input.pressed[sbox.input.keys["W"]]:
            self.y -= 235 * delta
        if sbox.input.pressed[sbox.input.keys["S"]]:
            self.y += 235 * delta
        # If we use elif there, you can't stay still when you hold both keys.

        # Collision with the floor.
        if self.y < 0:
            self.y = 0
        elif self.y > sbox.height - self.height:
            self.y = sbox.height - self.height
    
    def ai_movement(self, delta):
        if self.ball.y > self.y:
            self.y += 235 * delta
        if self.ball.y < self.y:
            self.y -= 235 * delta

        if self.y < 0:
            self.y = 0
        elif self.y > sbox.height - self.height:
            self.y = sbox.height - self.height


class Ball(Entity):
    def __init__(self, x, y):
        super().__init__(sbox, 20, 20, x, y)
        self.reset() # will create function later

    def reset(self):
        self.center()
        self.h_dir = random.choice((-1, 1)) # backwards or forwards
        self.v_dir = random.choice((-1, 1)) # up or down

    def ball_movement(self, delta):
        self.x += 250 * self.h_dir * delta
        self.y += 250 * self.v_dir * delta

        if self.y <= 2 or self.y >= sbox.height - 20:
            self.v_dir *= -1
        if self.x <= 0:
            self.reset()
        elif self.x >= sbox.width:
            self.reset()

player = Paddle(50, 0)
player.center_y() # center the y axis. built-in function.

ball = Ball(0, 0)

enemy = Paddle(sbox.width - 50, 0)
enemy.center_y()

@sbox.addUpdater
def update(delta):
    if ball.collide(player) or ball.collide(enemy):
        ball.h_dir *= -1

    player.player_movement(delta)
    ball.ball_movement(delta)
    enemy.ai_movement(delta)

@sbox.addDrawer
def draw():
    player.draw()
    ball.draw()
    enemy.draw()

@sbox.init
def init():
    enemy.ball = ball

sbox.mainloop()
```