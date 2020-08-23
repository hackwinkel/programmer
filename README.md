# programmer
Hardware design files for an ftdi based programmer for the hackwinkel badge and other ESP32 projects. 

This programmer uses an external 800mA 3.3V regulator to power the device to be programmed as the FT232RL can not reliably supply > ~80mA.

As the USB bus can only supply up to 500mA after negotiation, actual power output to the ESP32 is switched using the FT232 power enable output. Without negotiation power draw would be limited to 100mA, which is unsufficient for many ESP32 projects.

Please take care to only use this circuit with ESP32 boards with a maximum power draw of ~450mA, and only on a USB outlet capable of delivering 500mA of bus power, so this excludes unpowered USB hubs


