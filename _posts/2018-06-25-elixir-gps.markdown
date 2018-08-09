---
layout: post
title:  "Using Elixir with a GPS"
date:   2018-06-25 18:11:03 -0500
categories: elixir nerves
---
# Intro
__Note: Work in progress__

# Connect GPS to the Computer
There are a couple of ways to connect the GPS module to your compuer. You can use a USB to TTL Serial Converter cable, or you can use an Arduino.

## Connecting With USB to TTL Cable
* Green -> RX
* White -> TX
* Black -> Ground
* Red -> VIN
![GPS module connected to USB to Serial TTL converter]({{ site.baseurl }}/images/elixir_gps/gps_usb.png)
__Note: These wires are for the cable I am using. Yours may be different__

## Connecting With Arduino
* On the Ardunio, short RESET to GND
* 0/RX -> RX
* 1/TX -> TX
* 5V -> VIN
* GND -> GND
![GPS module connected to Arduino]({{ site.baseurl }}/images/elixir_gps/gps_arduino.png)

# Verify Connection
Again, there are a few different ways to view the NMEA sentences. You can use your trusty terminal, or you can use the Arduino IDE.
## Verify Connection with the Terminal
### Linux
1. Find what the path is to the USB device.
2. Set baud rate for the device by executing this command `stty -F /dev/ttyUSB0 9600`
   __Note: /dev/ttyUSB0 is the path to my USB device and 9600 is the baud rate to my GPS. Yours may be different__
3. View the data coming out with `cat /dev/ttyUSB0`
### Windows
__TODO: DO this__
### MacOS
This should be similar to Linux. I have no MacOS to verify this on.

