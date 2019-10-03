---
layout: post
title:  "Powerpoint Controller"
date:   2000-01-11 12:00:00 +0100
img: powerpoint_controller.jpg
tags: arduino powerpoint switch
github: aburnsni/powerpoint_controller
downloads:
hidden: false
---
# Powerpoint Controller

A simple powerpoint controller using 2 switch inputs to an Arduino Pro Micro.  These are converted to Left and Right arrow presses to navigate presentations.

Often used with foot switches while playing bass guitar.

{% highlight cpp %}
#include <Keyboard.h>
const int buttonPinL = 7;
const int buttonPinR = 6;
int buttonStateL = 0;
int buttonStateR = 0;
void setup() {
  pinMode(buttonPinL, INPUT);
  pinMode(buttonPinR, INPUT);
}
void loop() {
  buttonStateL = digitalRead(buttonPinL);
    buttonStateR = digitalRead(buttonPinR);
  if (buttonStateL == HIGH) {
    Keyboard.write(KEY_RIGHT_ARROW);
    delay(500);
  }
    if (buttonStateR == HIGH) {
    Keyboard.write(KEY_LEFT_ARROW);
    delay(500);
  }
}
{% endhighlight %}