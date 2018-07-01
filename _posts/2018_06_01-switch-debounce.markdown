---
layout: post
title:  "Switch Debouncer"
date:   2000-01-11 12:00:00 +0100
img: 
tags: arduino midi
github: aburnsni/sfx_switch_debounce
downloads:
hidden: false
---
# Switch Debouncer

Recently we replaced some rather aged components in a sensory garden.  The original design had switches set in the ground to trigger animal sounds when pressed.  Unfortunately the existing system had succumbed to the weather and was beyond rescue.  To replace with the same (yes it was still available) would have cost >£100.
I decided that in it's place we could use an [Adafruit SFX board][adafruit_sfx] along with a low cost amp from eBay.
We then discovered that the switches were also corroded and needed replacing - back to eBay!

Wired it up all up and it worked perfectly... Except, the buttons would occasionally get stuck.

After a few too may complaints from the neighbouring classrooms about the incessant BAA's and MOO's we had to do something about it.

## Serial control vs debounce

I had 2 options, either utilise the SFX boards Serial Interface, or just send signals directly to it's IO's.  The latter seemed easier.

Using an [Arduino Pro Mini][arduino_pro_mini] I connected 4 pins to the switches and 4 to the IO's on the Audio board.
It was programmed to ensure that the button sent a short (200ms) pulse HIGH when a button was pressed.  This would not repeat until the button was released.  Thus the problem of overly vocal farm animals was solved.

[adafruit_sfx]: https://www.adafruit.com/product/2341
[arduino_pro_mini]: https://store.arduino.cc/arduino-pro-mini