---
layout: post
title:  "Tippenny Guitar"
date:   2018-06-17 19:44:25 +0100
img: penny_guitar.jpg
tags: arduino midi
github: aburnsni/tippenny_guitar
downloads: penny_guitar_box.zip
hidden: false
---
The **Tippenny<sup id="a1">[1](#f1)</sup> Guitar** was one of my first arduino MIDI controllers.

# Hardware

## Shields

Built around an [Arduino Uno][arduino uno] and an Adafruit [Capacitive Touch Shield][touch shield].
British 2p coins were used as touch contacts.

## LEDs

The LED's are Charlieplexed, allowing 12 LED's to be  switched on and off via 4 pins on the UNO.  The problem with this is that errors can occur when multiple contacts are pressed.
An improvement on this would be to use 2x74HC595 shift registers to handle the LEDs.  This would also reduce the pin requirement to 3.

## Others

A standard 5-pin DIN socket provides MIDI connectivity.  Power is supplied by 6 AA sized batteries.  The Uno's USB socket is accessible to provide an alternative power source and to reprogram the UNO.

## The Case

The case was laser cut from 3mm MDF.  The main box template was designed at MakerCase.com.  The cut-outs for the coins, LEDs and sockets were then added.

# Software

Chords are played with a 5ms delay between each note to give a more natural guitar effect.

MIDI notes and chords are defined as follows:
{% highlight arduino %}
#define NOTE_C3 4
#define NOTE_CS3 49
#define NOTE_Db3 49
#define NOTE_D3 50

int CHORD_C[] = {0, NOTE_C3, NOTE_E3, NOTE_G3, NOTE_C4, NOTE_E4};
int CHORD_D[] = {0, 0, NOTE_D3, NOTE_A3, NOTE_D4, NOTE_FS4};
{% endhighlight %}

The "0"s in the chords allow for unused strings in the guitar chords.

<b id="f1">1</b> [http://www.dsl.ac.uk/entry/snd/tippenny][tippenny] [↩](#a1)

[tippenny]: http://www.dsl.ac.uk/entry/snd/tippenny
[arduino uno]: https://store.arduino.cc/arduino-uno-rev3
[touch shield]: https://www.adafruit.com/product/2024