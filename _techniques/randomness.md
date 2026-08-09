---
title: Randomness & Generative Control
slug: randomness
accent: sky
description: sometimes, degradeBy, perlin, and other sources of controlled chaos.
---

Strudel has several built-in sources of randomness that stay musically
useful because they're deterministic per-cycle rather than fully chaotic.

## Thinning a pattern

<div class="strudel-embed">
  <div class="embed-label">
    <span>degradeBy removes events probabilistically</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
s("hh*16").degradeBy(0.5)
    -->
  </strudel-repl>
</div>

## Random note choice

<div class="strudel-embed">
  <div class="embed-label">
    <span>irand picks a random integer each step</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
n(irand(8).segment(8)).scale("C minor").s("piano")
    -->
  </strudel-repl>
</div>

## Smooth random motion

<div class="strudel-embed">
  <div class="embed-label">
    <span>perlin noise for organic modulation</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
n("0 3 5 7").s("sawtooth")
  .lpf(perlin.range(200, 4000).slow(4))
    -->
  </strudel-repl>
</div>

## Tips

- `.degradeBy(x)` and `.sometimesBy(x, fn)` both take a probability 0–1 — start subtle (0.1–0.3) unless you want heavy variation.
- `irand(n)` gives a hard-edged random integer; `perlin` gives smooth continuous randomness — pick based on whether you want steps or drift.
- `irand`, `perlin`, `sine` and friends are *continuous* signals with no onsets of their own — used inside `n(...)`/`note(...)` alone, nothing will trigger. Give them structure with `.segment(n)` (sample n times per cycle) or `.struct("x(3,8)")` (trigger on a rhythm), or use them to modulate a parameter of an already-discrete pattern like `.lpf(perlin.range(...))`.
- Because Strudel's randomness is seeded by cycle count, patterns stay reproducible when you share code, unlike true random noise.
