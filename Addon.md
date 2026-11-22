# Addon boards

Snowdive CPU boards (top boards) allow for addons. The most well-known (and currently the only) addon is the palmtop addon board - essentially being a palmtop conversion kit for your Snowdive board.

Other possible future addons include: a tablet conversion kit, a QWERTY handheld conversion kit, a gaming console base, a multi-sensor base, or simply a USB port breakout.
In general, the addon port is designed to help you build the Snowdive CPU board into other devices, no matter if you're building a robot or a desk clock.

Addons are connected through the two bottom ports on Snowdive, using cheap and abundant cabling and a reasonable pinout:

`render of the FFC connectors`

The addon interface includes:

- Up to 20W of input/output power (with contacts capable of carrying up to 5V/4A) (`VSYS`)
- Two USB ports from the onboard USB hub
- The I2C port from the CPU, together with one GPIO usable as INT (`EC_INT`)
- Two GPIOs from the SBC (`IO1`/`IO2`) (optional, have to be jumpered to the board)
- One 3.3V input (`3.3V_EC`), allowing parts of the board (GPIO expanders and the like) to be powered when the SBC is powered off
- One `EC_PRESENT` signal, allowing for takeover of some onboard I2C peripherals by the addon (I2C expanders and the like)
- One EC I2C port input, used for I2C peripheral takeover by the EC
- Two INT signals from the EC (coming from the the I2C GPIO expanders).
- Neopixel LED input, wired to the two Neopixels

`pinout1`

`pinout2`

Each digital pin is duplicated for resilliency, and there's plenty of GND. The FFC cabling is 30-pin 0.5mm, easy to find. You can find such cables of all sorts of different lengths on Amazon/Aliexpress/etc.
If you want a more reliable source, [use LCSC](https://www.lcsc.com/category/86.html?scene=FULL_MATCH&globalKeyword=JS05A-30P&s_z=n_q_JS05A-30P) and search for `JS05A-30P`.

Reference: [cables used on the Snowdive palmtop](https://www.lcsc.com/product-detail/C53190744.html?s_z=n_q_JS05A-30P).
