# Palmtop base expansion interfaces

The Snowdive palmtop base has a number of expansion interfaces.

<img width="1620" height="1306" alt="palmtop1" src="https://github.com/user-attachments/assets/8c81c2ec-19bc-4c4e-a6f2-13cd0fa0b55f" />

1) Addon USB (QWIIC-like USB pinout), with 3.3V or 5V switchable output voltage. Use it to attach a WiFi card or any other similar addon. Output power limit 500mA.
2) EC I2C socket (external-facing). Usage generally requires modifying the RP2040 firmware. Output power limit 500mA.
3) EC I2C socket (unpopulated). Usage generally requires modifying the RP2040 firmware.
4) Touchpad addon port, with 3.3V, 5V, two RP2040 GPIOs, two I2C expander GPIOs, and EC I2C. Can be used for adding a touchpad, a trackpad, a trackpoint, a joystick, or some other addon.
5) A scrollwheel footprint. Shares its two GPIOs with the touchpad addon port.
6) Solderable pad footprints for CPU-connected I2C addons, with two extra GPIOs available for INT and other purposes, as well as a PWM pad.
7) Temperature sensor input connected to the charger IC, letting the charger detect battery overtemperature and undertemperature events.

<img width="1620" height="1306" alt="palmtop2" src="https://github.com/user-attachments/assets/fe4544d2-e0da-4521-9129-da763bb0fef8" />
