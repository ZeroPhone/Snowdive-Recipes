# Expansion port

<img width="1614" height="493" alt="Screenshot_20261122_055745" src="https://github.com/user-attachments/assets/709584a3-229b-4143-ad22-7834d1c09a75" />

The 23-pin expansion port on top of the Snowdive palmtop gives you an ability to do hardware hacking of all sorts:

- prototype on breadboards/protoboards using jumper wires
- reverse-engineer hardware
- use one of the pre-designed expansion boards
- create your own expansion boards

<img width="1614" height="493" alt="Screenshot_20261122_055758" src="https://github.com/user-attachments/assets/f7524489-910f-4da2-815d-6775f5f199c7" />

All signal pins are 3.3V level. All the pins are ESD-protected, and further current-limited/ringing-dampened by series resistors. All three available power rails are current-limited.

Power rails available on the expansion board:

- 3.3V/0.5A
- 5V/0.5A
- "VBAT" (3.7/1A)

Interfaces available on the expansion board:

- **GPIO**
- **I2C**
- **UART**
- PWM
- SPI
- I2S
- SDIO

Interface availability is heavily dependent on the SBC you use. Only GPIO/I2C/UART are guaranteed.
All aforementioned interfaces are available when using the Pi Zero, but only some (generally I2C and UART) are available when using a different SBC.
Until a compatibility table is compiled, you can start by mapping the pinout below to your own SBC, or check the [SBC pin compatibility spreadsheets in Snowdive-Ports repository](https://github.com/ZeroPhone/Snowdive-Ports/tree/main/docs) to learn more.

# Existing addon boards

A number of expansion boards have been designed for the expansion header, available for manufacturing or reuse for your own designs. Available expansion boards:

- [LoRa board](https://github.com/HackModsOrg/lora-blepis) (untested)
- [LTE board](https://github.com/HackModsOrg/lte-blepis) (work in progress)
- [Audio codec board](https://github.com/CRImier/MyKiCad/tree/master/Ecosystems/blep_audio) (untested)
- [I2C/SPI chip flashing board](https://github.com/CRImier/MyKiCad/tree/master/Ecosystems/blep_hackerboard) (untested)
- [CatPatHat]() (untested)

# Pinout

When facing the display (normal orientation), from left to right:

| Number | Name   | Purpose (all SBCs) | Purpose (Pi Zero) | Notes |
| ------ | ------ | ------------------ | ----------------- |-------|
| 1 | 5V/0.5A | | | |
| 2 | GND | | | |
| 3 | 3.3V/0.5A | | | |
| 4 | I2C SDA | SBC physical pin 3 | GPIO 2 (always I2C) | | 
| 5 | I2C SDA | SBC physical pin 5 | GPIO 3 (always I2C) | |
| 6 | GPIO  | SBC physical pin 7 | GPIO4 | Can be used for PITX on RPi|
| 7 | GND | | | |
| 8 | UART TXD | SBC physical pin 8 | GPIO14 (always UART) | Generally debug UART, but can be switched into GPIO mode |
| 9 | UART RXD | SBC physical pin 10 | GPIO15 (always UART) | Generally debug UART, but can be switched into GPIO mode |
| 10 | GPIO | SBC physical pin 12 | GPIO18 | Can be used for PWM on RPi |
| 11 | GPIO | SBC physical pin 11 | GPIO17 | Can be used for PWM on RPi |
| 12 | GPIO | SBC physical pin 13 | GPIO27 | Can be used for SDIO on RPi |
| 13 | GPIO | SBC physical pin 15 | GPIO22 | Can be used for SDIO on RPi |
| 14 | GPIO | SBC physical pin 16 | GPIO23 | Can be used for SDIO on RPi |
| 15 | GPIO | SBC physical pin 18 | GPIO24 | Can be used for SDIO on RPi |
| 16 | GPIO | SBC physical pin 22 | GPIO25 | Can be used for SDIO on RPi |
| 17 | GPIO | SBC physical pin 37 | GPIO26 | Can be used for SDIO on RPi |
| 18 | GPIO | SBC physical pin 35 | GPIO19 | Can be used for SPI/I2S on RPi |
| 19 | GPIO | SBC physical pin 36 | GPIO16 | Can be used for SPI/I2S on RPi |
| 20 | GPIO | SBC physical pin 38 | GPIO20 | Can be used for SPI/I2S on RPi |
| 21 | GPIO | SBC physical pin 40 | GPIO21 | Can be used for SPI/I2S on RPi |
| 22 | GND | | | |
| 23 | 3.7V/1A | | | |
