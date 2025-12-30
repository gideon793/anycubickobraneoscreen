# Using the Anycubic Kobra Neo screen with Klipper

## Using a Raspberry Pi4 as the host

Flash the SD card using Mainsail OS

Using the LCD screen as well as a webcam may cause undervoltage to be reported. I used a RPi5 powersupply rated as 20W with which there were no further warnings.

There were signficant problems with the onboard WiFi with inability to connect via SSH or though the webpage. I used a USB dongle with which the connection as been stable so far. I had similar problems with the RPi3B+ as regards to WiFi and will have to test the same settings with it.

## Connections

Wire the pi to the Screen as described in this repository: https://github.com/jokubasver/Anycubic-Kobra-Go-Neo-LCD-Driver/

_Note that the order of the pins properly. I spent a whole day with the order reversed because the image is of the connector to the printer mainboard_

Some online guides report that the __ST7796__ require 3.3V but you clearly have to connect the 5V pin. 

_Remember to wire the encoder pins as well since the knob can be functional as well_

