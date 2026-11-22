# QWIIC

The Snowdive board carries a number of QWIIC and QWIIC-like interfaces.
You can use them to connect any of the various QWIIC peripherals available on the market,
or just use them a general I2C ports with a very nice connector and known pinout.

<img width="1501" height="1158" alt="qwiic1" src="https://github.com/user-attachments/assets/a6b9fe53-9f78-4982-a4e6-7d0aa086d648" />

All QWIICs on the top ZERO board have a 3.3V power rail.

1) QWIIC connected to the SBC's main I2C bus. Current-limited to 500mA.
2) QWIIC connected to the SBC's main I2C bus, for internal use.
3) QWUART (QWIIC UART) connected to the SBC's main UART bus through a mux, for internal use. See [UART addon](UART_addons.md) for usage instructions.
4) QWUSB (QWIIC USB) connected to the ESP32's USB port, used for programming the ESP32 addon if present. The VCC pin is normally disconnected, but can be jumpered to the ESP32 3.3V rail.
5) QWUSB (QWIIC USB) connected to the LTE modem's USB port. Can be used to reclaim the free USB port when the modem is absent. Current-limited to 500mA, shares the current limit with the USB hub, power off when USB in passthrough mode (hub powered off).


