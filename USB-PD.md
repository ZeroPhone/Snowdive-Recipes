# USB-PD interfaces

There is one USB-PD interface (FUSB302B) available on the Snowdive top board, connected to the one (and only) USB-C port on the board.

It's muxed between SBC I2C and EC I2C if an addon (like the palmtop addon) is present,
with an ability to connect the FUSB302 to SBC I2C at will by switching a GPIO on the I2C GPIO expander (the `mux_fusb` sysfs node).
This FUSB302B supports dead battery mode (Rd presented when circuit powered off), so that the top board can be powered through its USB-PD port.

A ZPUI app (`Hardware`=>`PD tools`) is available for rudimentary use of the PD interface - at the moment, merely source/sink/audio adapter detection (Rd/Rp/Ra).
More functionality (profile inspection and data transfer over PD) is coming.

FUSB302 INT is connected to an I2C GPIO expander. That makes it inaccessible in palmtop mode, unless the RP2040 palmtop EC firmware is modified to support its handling in the future.

There is another USB-PD interface (FUSB302B01) available on the palmtop addon board. It is exclusively connected to the onboard RP2040 EC, there to be used for USB-C charging PD negotiation, and not available to the SBC.

- [Example code](https://github.com/CRImier/AltmodeFriend) that can be adapted for handling USB-PD from Linux userspace
- [PD tools ZPUI app source code](https://github.com/ZeroPhone/ZPUI/tree/master/apps/hardware_apps/pdtools)
