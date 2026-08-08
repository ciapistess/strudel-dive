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

<div class="strudel-embed">
  <div class="embed-label">
    <span>modulated lowpass</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
n("0 3 5 7").s("sawtooth")
  .lpf(sine.range(300, 3000).slow(4))
    -->
  </strudel-repl>
</div>

## Space: reverb & delay

<div class="strudel-embed">
  <div class="embed-label">
    <span>reverb + rhythmic delay</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
n("0 ~ 3 ~").s("piano")
  .room(0.6)
  .delay(0.375)
  .delayfeedback(0.4)
    -->
  </strudel-repl>
</div>

## Grit

<div class="strudel-embed">
  <div class="embed-label">
    <span>distort + bitcrush</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
s("bd*4").distort(2).crush(6)
    -->
  </strudel-repl>
</div>

## Tips

- Any numeric effect parameter can be a pattern (`"0.2 0.8"`) or a
  continuous signal (`sine`, `perlin`, `saw`), not just a fixed number.
- `.delay()` values that are rhythmic fractions of the cycle (like `0.375` = 3/8) lock the echo to the groove.
- Reach for `.room()` before adding more layers — space often reads as "fuller" than more notes.
