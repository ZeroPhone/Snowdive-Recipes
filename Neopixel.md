# Neopixel LEDs

The Snowdive top board and addons (the bottom board) each have two Neopixel LEDs.

When using a Snowdive top board standalone:

- Short-circuit the JP12 jumper (with solder or conductive tape)
- Drive the two Neopixel LEDs from SBC's physical pin 32 (RPi GPIO 12), using something like the `rpi_ws281x` toolkit. Top right LED is first in chain, top left LED is second in chain.

When using a Snowdive palmtop configuration:

- The RP2040 EC on the palmtop board is responsible for driving all 4 LEDs. **Do not short-circuit the JP12 jumper** under any circumstances.
- You can use the beepy-kbd driver to drive any of these 4 LEDs, as numbered below:

- In Python, you can use the `beepy` library that's bundled in the `zpui_lib` package:

```python
from zpui_lib.libs.hw import beepy as beepy_lib
```
