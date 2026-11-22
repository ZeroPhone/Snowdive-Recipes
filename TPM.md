# TPM addon

<img width="1800" height="868" alt="tpm2" src="https://github.com/user-attachments/assets/7e24362e-c0c3-4045-a794-269540dc5e64" />

A `ST33KTPM2X32DKG9` (or compatible) chip from STSAFE-TPM series can be soldered onto the TPM footprint on the Snowdive ZERO board, exposing TPM capabilities to the Linux OS running on your SBC.
It is connected to both I2C (main bus) and SPI (SPI0CS0) interfaces. It can be disconnected from either of the interfaces by moving/removing series resistors.

When TPM chip is not soldered on, a 10-pin FFC socket can be exposed instead, by scratching off the solder mask over the signal pads.
This allows connection of an addon for LoRa, an extra display, or other SPI-connected expansion boards.

More info:

- [Product page](https://www.st.com/en/secure-mcus/st33ktpm2x.html)
- [meta-st-x-linux-tpm repository](https://github.com/STMicroelectronics/meta-st-x-linux-tpm)
- in particular, [the kernel patchsets therein](https://github.com/STMicroelectronics/meta-st-x-linux-tpm/tree/main/recipes-kernel/linux/linux-stm32mp)
- [STPM4RasPI development kit documentation](https://www.st.com/en/evaluation-tools/stpm4raspi.html)
- [X-Linux-TPM expansion package wiki](https://wiki.st.com/stm32mpu/wiki/X-LINUX-TPM_expansion_package)



