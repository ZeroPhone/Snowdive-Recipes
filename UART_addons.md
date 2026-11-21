# GPS

<img width="1825" height="1950" alt="hadimg_use_qwiic_5a" src="https://github.com/user-attachments/assets/c3886dbf-b36b-4a53-a274-08a52a01bc01" />

You can connect a GPS (or any other UART peripheral) using the UART port on the Snowdive top board. The port is JST-SH 4p, and follows QWIIC pinout:

1. GND
2. 3.3V (not current limited, but budget between 100mA and 500mA depending on your SBC and other peripherals in use
3. RX (input, connect to TX on your device)
4. TX (output, connect to RX on your device)

From there, do this:

- Run `sudo systemctl stop serial-getty@ttyS0.service` after boot (command and port name may vary, use `systemctl -a | grep getty` to check)
- Alternatively, make sure UART login console is disabled, using `raspi-config` or other configuration tools. It's disabled by default on wireless-enabled Pis, anyway
- On WiFi-enabled Raspberry Pi Zero boards, put `dtoverlay=disable-bt` in your `/boot/firmware/config.txt` to make sure you're getting a UART with a stable baudrate
- On other platforms, see if you require a device tree overlay to make UART work on physical pins 8/10

By default, the internal expansion port is disconnected from SBC UART on pins 8 and 10. You need to disconnect it from top expansion port.
This can be done after installing and loading the `beepy-kbd` driver:

- `sudo sh -c "echo 1 > /sys/firmware/beepy/uart_mux"`

After this, you can open your UART using `screen` or `tio`. `tio` is the preferred way; install it with `sudo apt install tio`. Common baudrate for GPS chips is 9600.

- `sudo screen /dev/ttyS0 9600` (port may differ), or
- `sudo tio /dev/ttyS0 -b 9600` (port may differ)

Use `Ctrl+T q` to exit `tio`. Use `Ctrl+A k y` to exit `screen`.
