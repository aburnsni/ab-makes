---
layout: post
title:  "Minecraft Contoller"
date:   2018-06-21 12:00:00 +0100
img: arduino.jpg
tags: arduino keyboard art
github: aburnsni/touch_micecraft_keyboard
downloads:
hidden: false
---
This is a project assisting a GSCE Art student who wanted to design a 3D custom keyboard controller for Minecraft.

I was called in to help with the electronics and programming of the hardware.  As the project was for Art, he is only marked on the design aspects of the device.  The exam does not require the device to be operational.

It was decided that although it was not required to be operational that it would be a relatively easy for me to build in the necessary electronics.

# Hardware

## Case

Not my responsibility :)  This was designed by the student, although I was able to provide some CAD advice.

## Electronics

We wanted capacitive touch buttons that would send keyboard signals to the PC.  This was acheived the the use of an [Arduino Pro Micro][pro_micro] and an [Adafruit MPR121 12-Key Capacitive Touch Sensor][mpr121].  The ATMega32u4 on board the Pro Micro has one big advantge over the ATmea328 used on other Arduino devices.  The ATMega32u4 has onboard USB tranceiver which allows th Pro Micro to be used as an HID-class USB device.  This means that it can very easily emulate a keyboard or mouse.

## Software
The programming simply mapped a touch signal to a specific keyboard press.

[pro_micro]: https://www.sparkfun.com/products/12640
[mpr121]: https://learn.adafruit.com/adafruit-mpr121-12-key-capacitive-touch-sensor-breakout-tutorial/overview