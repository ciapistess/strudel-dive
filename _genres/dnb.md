---
title: Drum & Bass
slug: dnb
accent: amber
description: Fast breaks, chopped amens, sub-bass, syncopated snares.
---

DnB lives around 160–175 bpm with the groove concentrated in the break, not
the kick. In Strudel, set a fast `setcps` and build the break as its own
pattern you can chop independently from the bass.

## The break

<div class="strudel-embed">
  <div class="embed-label">
    <span>basic broken beat</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(1.4)
s("bd ~ sn ~ ~ bd sn ~")
  .bank("RolandTR909")
    -->
  </strudel-repl>
</div>

## Sub-bass under the break

<div class="strudel-embed">
  <div class="embed-label">
    <span>reese-ish sub bass</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(1.4)
n("<0 0 3 0>").s("sawtooth")
  .lpf(200)
  .note(-24)
  .gain(0.9)
    -->
  </strudel-repl>
</div>

## Tips

- Chop a sample into 16ths with `.chop(16)` and reorder with `.striate()` or
  pattern strings to build amen-style breaks quickly.
- Keep the sub monophonic and simple — DnB low end works best with one clear
  note at a time, not chords.
- Automate `.crush()` or `.distort()` sparingly on the break to add grit without losing punch.

---

*Content coming: liquid DnB pads, jump-up bass design, half-time reinterpretation.*
