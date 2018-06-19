---
layout: post
title:  "Tipenny Guitar"
date:   2018-06-17 19:44:25 +0100
img:
tags: arduino midi
github: aburnsni/tippeny_guitar
---
The Tipenny Guitar was one of my first arduino MIDI controllers.
Built around an Arduino Uno and an Adafruit touch shield.

{% highlight c# %}
<MIDI.h>
void setup() {
MIDI.begin();
}
void loop() {
}
{% endhighlight %}