---
layout: post
title:  "Programable MIDI switch box"
date:   2018-06-17 19:44:25 +0100
img:
tags: midi arduino
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

[Git Repository][git-rep]

[git-rep]: https://github.com/aburnsni/programmable_midi_switch_box