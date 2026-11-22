# Displays and display hacking

Snowdive supports dozens of different display options, with help of 8 different physical interfaces. You can either plug or solder on a common display found online, adapt a less common but way cooler display, or instead use the onboard pin sockets to build yourself a touchscreen eInk handheld.
It's completely up to you.

1. ILI9341 and ST7789 18-pin displays (2.4"/2.8"/3.2"/etc, 320x240, backlit LCD. resistive and capacitive touch options exist)
2. Sharp LS027B7DH01 memory LCD (2.7", 400x240, monochrome. sunlight-readable but backlit/frontlit options exist)
3. JDI LPM027M128 (2.7", 400x240, 4-bit color, sunlight-readable but backlit/frontlit versions exist)
4. Sharp LS032B7DD02 memory LCD (3.2", 336x536, monochrome. sunlight-readable backlit/frontlit options exist)
5. ILI9488 and compatible 40-pin displays (3.5"/4.0", 480x320, backlit LCD)
6. eInk/RLCD/other displays, using the 8-pin 2.54mm solderable header on the board. (from 2" to 4", up to 480x320 generally) 
7. I2C displays using the onboard I2C port (up to 128x64 and monochrome generally). This lets you have a second (smaller) display on your Snowdive, for notifications and other purposes.
8. General SPI displays using the second SPI port found under the [TPM](TPM.md) chip footprint. This lets you have a second (smaller) display on your Snowdive - for instance, an eInk display on the back.

As a result, you can simply use one of the numerous off-the-shelf displays and pay no mind to all the numerous options, or instead experiment with cool display technologies using Snowdive as a base. Completely up to you.

`display&touch picture: front`
`display&touch picture: back`

For non-backlit displays, there's a 2-pin PWM backlight header available, already equipped with a current limit resistor.

There are two I2C headers available for touchscreen addition purposes, too. One is connected to I2C0 (pins 27/28) and another is connected to I2C1 (pins 3/5).
Both provide two GPIOs: one INT-intended GPIO directly from the SBC, and one RST-intended GPIO directly from an IO expander.

The 40-pin display header is wired for a specific (popular) kind of 40-pin ILI9488 display. However, it also lets you create FFC adapters to other kinds of FFC-adorned and solderable displays.
For that, it even adds I2C (I2C1) touchscreen support using a normally-unpopulated resistor 4-pack, which you can either populate or simply short-circuit-connect with thin wires, accomodating I2C touchscreen displays of your choice.

Snowdive ZERO top board can in theory accomodate higher-res DSI displays, for instance, common 4" 800x480 color panels, like the one found on Tanmatsu.
However, that requires a DSI header on the SBC itself. Most SBCs in the Zero formfactor don't provide such an option, with the exception being MangoPi MQ-Pro and Luckfox Lyra Zero W.
