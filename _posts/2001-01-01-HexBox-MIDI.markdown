---
layout: post
title:  "HexBox MIDI"
date:   2018-05-11 12:00:00 +0100
img: hexbox_midi.jpg
tags: arduino midi
github: aburnsni/honeycomb_midi
downloads:
hidden: false
---
# Hexbox MIDI
The Hexbox MIDI is another capacitive touch MIDI controller.  It works in a similar method to the [Tippenny Guitar]({% post_url 2018-06-17-tippenny-guitar %})

## Parts
###  Hardware
- [Arduino Pro Micro][pro_micro]
- [MPR121 touch controller][mpr121]
- 5 pin DIN socket (MIDI socket)
- LiPo battery
- TP4056 LiPo charger
- WS2812B LED strip
- Brass buttons x12

### Software
- [NeoPixelBus][neopixelbus]
- [Adafruit_MPR121][mpr121]

### Case
The case was designed in Fusion 360 and printed in PLA.  Transparent PLA was used for the main body to allow the led lights to be seen.

## Operation
Each cell of the case is lit by a WS2812 LED each set to a different coloour.  The buttons are used as the capacitive touch sensors.
As the buttons are touched the LED is set to white and a MIDI "NOTE ON" is sent.  On release the LED resets and a "NOTE OFF" signal is sent.




[pro_micro]: https://www.sparkfun.com/products/12640
[mpr121]: https://learn.adafruit.com/adafruit-mpr121-12-key-capacitive-touch-sensor-breakout-tutorial/overview
[neopixelbus]: https://github.com/Makuna/NeoPixelBus
[mpr121]: https://github.com/adafruit/Adafruit_MPR121