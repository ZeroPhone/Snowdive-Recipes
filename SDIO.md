# SDIO hacking

<img width="1712" height="930" alt="sdio2" src="https://github.com/user-attachments/assets/2153eb9d-b0b1-415d-8cce-e55e3d141ca1" />

There is an ESP32-C5 footprint in the top center of the Snowdive board, originally for use with [esp-hosted](https://hackaday.com/2026/10/07/esp32-as-your-raspberry-pis-linux-wireless-co-processor/).
It is mainly designed to support ESP32-C5 and ESP32-C6 wireup, but it can support other SDIO devices, like microSD cards and eMMC chips, too.

The SDIO link is only confirmed to function when used with a Raspberry Pi Zero 1/1W/2W. So far, no other boards have confirmed SDIO capabiliuty on the same pins as the Raspberry Pi boards.
It also requires turning off the onboard WiFi adapter in `/boot/firmware/config.txt` on 1W and 2W boards, as well as disabling the Bluetooth capability (since the SDIO interface is used to upload BT firmware, afaict).

<img width="1712" height="1055" alt="sdio1" src="https://github.com/user-attachments/assets/88ac67d9-8d3e-4a83-bc13-9fd8b570bb12" />

*ESP32-C5 populated (TODO depopulated resistors are not shown correctly on this picture)*

By default, the SDIO link is wired up to the top expansion 23-pin socket. Using the ESP32-C5 footprint with SDIO requires desoldering resistors R97,R98,R99,R100,R101,R102, as well as ESD diodes U10 and U23.

- The ESP32-C5-WROOM module (non-MINI) is supported natively on the footprint, both PCB antenna (-1) and uFL (-1U) versions.
-- Care needs to be taken to avoid soldering the smaller pads in the middle of the SDIO link, which are used for ESP32-C6 compatibility.
-- By default, the ESP32-C5 will only work in 1-bit mode. You must move two resistors to enable 4-bit mode: from R139,R140 to R141,R142. This will disable USB programming, so make sure your firmware works in 1-bit mode beforehand.
- The ESP32-C6-WROOM module (non-MINI) is supported natively on the footprint, both PCB antenna (-1) and uFL (-1U) versions.
-- Six marked SDIO tracks under footprint the need to be cut to avoid creating a stub.
-- Solder blobs need to be used to complete the SDIO connection, due to ESP32-C5 compatibility being prioritized.

The ESP32-C5 and ESP32-C6 can be used as a general wireless coprocessor after modifying esp-hosted and adding extra wireless hardware into the mix,
as speculated in [the esp-hosted article](https://hackaday.com/2026/10/07/esp32-as-your-raspberry-pis-linux-wireless-co-processor/).
They can also be used for running any of the multiple community-provided custom firmware images.

Drop-in boards for microSD cards or eMMC chip/sockets, as well as arbitrary GPIO use, can be designed if you want to expand onboard storage of your Snowdive board instead of gaining WiFi capabilities.
The footprint exposes two I2C expander GPIOs (used for EN and BOOT control).




