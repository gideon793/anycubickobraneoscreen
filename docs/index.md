# Using the Anycubic Kobra Neo screen with Klipper

## Using a Raspberry Pi4 as the host

### Flash the SD card using Mainsail OS

Using the LCD screen as well as a webcam may cause undervoltage to be reported. I used a RPi5 powersupply rated as 20W with which there were no further warnings.

There were signficant problems with the onboard WiFi with inability to connect via SSH or though the webpage. I used a USB dongle with which the connection as been stable so far. I had similar problems with the RPi3B+ as regards to WiFi and will have to test the same settings with it.

_The onboard WiFi has to be disabled in order for the dongle to work_

Add `dtoverlay=disable-wifi` to `/boot/firmware/config.txt` to disable the onboard adapter

Set a static IP using nmtui: `sudo nmtui` and change the settings as required

## Config files for the Printer

I got these from the excellent guide: https://github.com/1coderookie/KobraGoNeoInsights

I did get frequent layer shifts with these settings though and I reduced the acceleration to 1500.

I also have a very bad bed requiring signficant tramming with poor success. I change the settings for the bed mesh to help deal with this. 

## Connections

Wire the pi to the Screen as described in this repository: https://github.com/jokubasver/Anycubic-Kobra-Go-Neo-LCD-Driver/

_Note that the order of the pins properly. I spent a whole day with the order reversed because the image is of the connector to the printer mainboard_

Some online guides report that the __ST7796__ require 3.3V but you clearly have to connect the 5V pin. 

_Remember to wire the encoder pins as well since the knob can be functional as well_

## Driver

There seems to be an inbuilt driver that can be used with displays on the newer raspios.

I found this thread that really helped me: https://forums.raspberrypi.com/viewtopic.php?t=380704 .

### I made a firmware files for the Linux display driver panel-mipi-dbi:

Source: Anycubic Kobra Neo Marlin fork [BSP SPI TFT driver](https://github.com/jokubasver/Kobra_Neo/blob/d3406176308f1839130edc08825f500a72c02f64/source/board/bsp_spi_tft.cpp#L406C12-L406C12). 


