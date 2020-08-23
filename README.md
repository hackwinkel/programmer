# programmer
Hardware design files for an ftdi based programmer for the hackwinkel badge and other ESP32 projects. 

This programmer uses an external 800mA 3.3V regulator to power the device to be programmed as the FT232RL can not reliably supply > ~80mA.

As the USB bus can only supply up to 500mA after negotiation, actual power output to the ESP32 is switched using the FT232 power enable output. Without negotiation power draw would be limited to 100mA, which is unsufficient for many ESP32 projects.

Please take care to only use this circuit with ESP32 boards with a maximum power draw of ~450mA, and only on a USB outlet capable of delivering 500mA of bus power, so this excludes unpowered USB hubs

The PCB contains a footprint of a 28 pin FT232RL integrated circuit AND a through-hole footprint of a common FTDI breakout module. Either can be fitted, but NOT both

The PCB also contains two buttons for manual programming initialization: one connected to the ESP32 RESET pin and one connected to the ESP32 GPIO0 pin. To program an ESP32 either let the software take care of toggling the RTS and DTR lines OR press and hold the GPIO0 button, then press and release the RESET button, then release the GPIO0 button. To manually reset the ESP32, simply press and release the RESET button



