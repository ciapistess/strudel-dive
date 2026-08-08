---
title: Lo-fi Hip-Hop
slug: lofi
accent: amber
description: Dusty swung drums, jazzy sampled chords, tape-saturated textures.
---

Lo-fi's whole identity is imperfection: swung, slightly-behind drums, warm
saturated chords, and enough noise/crackle to feel like a record. In Strudel,
swing and subtle detuning matter more than the note choices themselves.

## Swung drums

<div class="strudel-embed">
  <div class="embed-label">
    <span>swung boom-bap drums</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.45)
stack(
  s("bd ~ ~ bd ~ ~ bd ~"),
  s("~ sn ~ ~ ~ sn ~ ~"),
  s("hh*8").swingBy(1/3, 8).gain(0.5)
)
    -->
  </strudel-repl>
</div>

## Dusty chords

<div class="strudel-embed">
  <div class="embed-label">
    <span>detuned crushed epiano</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.45)
n("0 .. 3").chord("min7")
  .s("gm_epiano2")
  .detune(0.1)
  .crush(6)
  .room(0.3)
  .gain(0.7)
    -->
  </strudel-repl>
</div>

## Tips

- `.swingBy(1/3, 8)` on the hats is usually enough to move a pattern from "quantized" to "lo-fi."
- Light `.crush()` (values around 6–8) emulates cheap sampler bit depth without destroying the sound.
- A very subtle `.detune()` on chords fakes worn tape pitch instability.

---

*Content coming: vinyl-crackle layering, jazzy ii-V-I progressions in `.chord()`.*
