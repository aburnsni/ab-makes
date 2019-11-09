---
layout: post
title:  "Programable MIDI switch box"
date:   2018-06-17 19:44:25 +0100
img: prog_midi_switch.jpg
tags: midi arduino
github: aburnsni/programmable_midi_switch_box
downloads:
hidden: false
---
# Description
The box accepts multiple switch inputs.  Any momentary contact switch is supported via 3.5mm (1/8in) jack inputs.  The note, MIDI channel and velocity of each switch is independantly set using the rotary encoder.

# Hardware
The control box is based on an [Arduino Nano][arduino_nano].  Switch inputs are 3.5mm jack sockets using  the arduinos internal pullups.
A [rotary encooder][rotary_encoder] is used to control option menus displayed on a [Nokia 5110 lcd diaplay][nokia_5110].  Switch presses are shown by LEDs above each input, due to a shortage of IO pins these are controlled via a [74hc595 shift register][74hc595].
MIDI signals are then sent through a standard 5pin DIN socket.

## Arduino pin allocations

|------|------|
| TX0      | MIDI out       |
| 2,3,4    | rotary encoder |
| 5,6,7,8  | lcd display    |
| 9        | lcd backlight  |
| 10,11,12 | shift register |
| A0-A5    | switch inputs  |

## Components
### Switch inputs
A variety of switches can be used.  Although primeraly designed for [buddy/jelly bean switches][switches] any momentary contact switch can be used.  The inputs are pulled high using the arduino INPUT_PULLUP with the switches pulling low.

### Shift register
For simplicty I would have connected each indicator LED to its own output pin, however the Arduino Nano doesn’t have enough pins.  [Charlieplexing][charlieplex] would have been an option if only 1 LED was ever lit at a time.  Since I will need miltiple LEDs lit I decided to use a shift register.
This allows me to independantly control the 6 LEDs with only 3 ouput pins.

### LCD display
The LCD is controlled with the [PCD8544 library][pcd8544].  RST, DC, DIN and SCLK are connected to pins 5,6,7 and 8.  Since these are all 3.3V lines, they have to go theough a level shifter.  CS is tied to GND.  The LED backlight is controlled by pin 9.

### Rotary encoder
As the rotary encoder uses Interupts it is connected to pins 2 and 3.  The press switch on it is commected to pin 4.

### MIDI out
The MIDI signal is connected through a 220ohm resister to the TX0 pin of the arduino.

### Enclosure
The box was designed in Fusion 360 and 3D printed in PLA.

## Software

## TODO
Add battery and charger circuit.




[arduino_nano]: https://store.arduino.cc/arduino-nano
[rotary_encoder]: https://playground.arduino.cc/Main/RotaryEncoders
[nokia_5110]: https://www.sparkfun.com/products/10168
[74hc595]: https://www.mouser.co.uk/ProductDetail/Texas-Instruments/SN74HC595N
[switches]: http://www.inclusive.co.uk/hardware/switches-and-switch-mountings/button-switches
[charlieplex]: https://en.wikipedia.org/wiki/Charlieplexing
[pcd8544]: https://github.com/adafruit/Adafruit-PCD8544-Nokia-5110-LCD-library
