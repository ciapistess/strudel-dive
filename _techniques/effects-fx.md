---
title: Effects & Sound Design
slug: effects-fx
accent: amber
description: Filters, reverb, delay, distortion — shaping sound after synthesis.
---

Effects in Strudel are chained methods on a pattern, and most of them accept
patterns themselves — meaning a filter cutoff can move over time just like a
note sequence can.

## Filters

{% capture code1 %}
setcps(0.6)
n("0 3 5 7").s("sawtooth")
  .lpf(sine.range(300, 3000).slow(4))
{% endcapture %}
{% include strudel-embed.html code=code1 title="modulated lowpass" %}

## Space: reverb & delay

{% capture code2 %}
setcps(0.6)
n("0 ~ 3 ~").s("piano")
  .room(0.6)
  .delay(0.375)
  .delayfeedback(0.4)
{% endcapture %}
{% include strudel-embed.html code=code2 title="reverb + rhythmic delay" %}

## Grit

{% capture code3 %}
setcps(0.6)
s("bd*4").distort(2).crush(6)
{% endcapture %}
{% include strudel-embed.html code=code3 title="distort + bitcrush" %}

## Tips

- Any numeric effect parameter can be a pattern (`"0.2 0.8"`) or a
  continuous signal (`sine`, `perlin`, `saw`), not just a fixed number.
- `.delay()` values that are rhythmic fractions of the cycle (like `0.375` = 3/8) lock the echo to the groove.
- Reach for `.room()` before adding more layers — space often reads as "fuller" than more notes.
