---
title: Ambient
slug: ambient
accent: sky
description: Slow evolving textures, generative pads, sparse rhythm.
---

Ambient patterns in Strudel usually drop the pulse almost entirely and let
slow modulation and long reverb tails carry the piece. `.slow()`, `.often()`,
and generative note choice (`.choose()`, `.perlin`) do most of the work.

## A drifting pad

<div class="strudel-embed">
  <div class="embed-label">
    <span>slow dorian pad</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.2)
n("<0 3 5 7 10>".slow(4)).scale("D dorian")
  .s("gm_pad_new_age")
  .room(0.9)
  .size(0.9)
  .gain(0.6)
    -->
  </strudel-repl>
</div>

## Generative sparkle

<div class="strudel-embed">
  <div class="embed-label">
    <span>sparse generative bells</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.2)
n(irand(12)).scale("D dorian")
  .s("gm_music_box")
  .degradeBy(0.7)
  .room(0.8)
  .delay(0.5)
  .gain(0.4)
    -->
  </strudel-repl>
</div>

## Tips

- `.degradeBy(x)` is the fastest way to turn a busy pattern into something
  sparse and organic — start high (0.6–0.8) and lower it to taste.
- Long `.room()` and `.size()` values do more to create "space" than adding more notes.
- Consider dropping percussion entirely and letting pitched texture carry the rhythm.

---

*Content coming: field-recording layering, generative harmony with `.scale` + `irand`.*
