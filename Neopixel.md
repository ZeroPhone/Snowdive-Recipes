# Neopixel LEDs

The Snowdive top board and addons (the bottom board) each have two Neopixel LEDs.

<img width="1501" height="249" alt="neopixel1" src="https://github.com/user-attachments/assets/bfc4fc7a-982a-436c-88c1-f35012570e13" />
<img width="1620" height="316" alt="neopixel2" src="https://github.com/user-attachments/assets/51facea2-942b-44a1-aa25-f8b0790c6e97" />

When using a Snowdive top board standalone:

- Short-circuit the JP12 jumper (with solder or conductive tape)
- Drive the two Neopixel LEDs from SBC's physical pin 32 (RPi GPIO 12), using something like the `rpi_ws281x` toolkit. Top right LED is first in chain, top left LED is second in chain.

<img width="905" height="868" alt="neopixel3" src="https://github.com/user-attachments/assets/6aab3a09-3681-49a1-81a9-8451dd283e4f" />

When using a Snowdive palmtop configuration:

- The RP2040 EC on the palmtop board is responsible for driving all 4 LEDs. **Do not short-circuit the JP12 jumper** under any circumstances.
- You can use the beepy-kbd driver to drive any of these 4 LEDs, as numbered below:

<img width="1620" height="316" alt="neopixel4" src="https://github.com/user-attachments/assets/4665f3ab-0961-440c-8739-97e4fdf56acc" />
<img width="1501" height="249" alt="neopixel5" src="https://github.com/user-attachments/assets/c47d1e5f-8c12-4c9b-a46c-64060f1d5a5d" />

- In Python, you can use the `beepy` library that's bundled in the `zpui_lib` package:

```python
from zpui_lib.libs.hw import beepy as beepy_lib
```

An example of LED driving can be found in [the `Pomodoro` ZPUI app code](https://github.com/ZeroPhone/ZPUI/blob/master/apps/personal/pomodoro/main.py).
