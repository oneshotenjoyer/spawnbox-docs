# spawnbox.Input()

Parameters:

```py
spawnbox.Input() # wow, this has zero parameters. :O
```
<hr />
Functions:

<br />

`updateMouse(event: SDL_Event)` - Updates the mouse position.

`getMousePos()` - Gets the mouse position.

<hr />

Properties:

<br />

`Input().pressed` - ***Technically*** a dictionary. If you supply a keycode, it will give you if it is pressed or not.

`Input().keys` - The keycode dictionary.

Keycodes supported by SpawnBox:
```
A, B, C, D, E, F, G, H, I, J, K, L, M, N, O,
P, Q, R, S, T, U, V, W, X, Y, Z, 1, 2, 3, 4,
5, 6, 7, 8, 9, 0, F1, F2, F3, F4, F5, F6, F7,
F8, F9, F10, F11, F12, F13, F14, F15, LCTRL,
RCTRL, LSHIFT, RSHIFT, LALT, RALT, HOME,
INSERT, DELETE, SPACE, PLUS, RETURN
```

`Input().mouse_pos` - Literally just `get_mouse_pos()`.