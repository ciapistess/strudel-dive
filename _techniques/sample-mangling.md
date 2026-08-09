---
title: Sample Mangling
slug: sample-mangling
accent: violet
description: Slicing, chopping, and manipulating samples in Strudel.
---

Strudel can slice a single sample into pieces and reorder, reverse, or
re-trigger them — the basis of breakbeat chopping and glitch textures.
The examples below use a real breakbeat sample (`breaks125`) from the
Dirt-Samples pack, loaded explicitly with `samples(...)` — sample names
like this aren't in Strudel's small built-in default set, so you need to
load the pack before the name exists. Swap in your own sample the same way.

## Chopping

<div class="strudel-embed">
  <div class="embed-label">
    <span>chop a break into 8 pieces</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
samples('github:tidalcycles/Dirt-Samples/master')
setcps(0.6)
s("breaks125").chop(8)
    -->
  </strudel-repl>
</div>

## Reordering with striate

<div class="strudel-embed">
  <div class="embed-label">
    <span>striate interleaves slices</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
samples('github:tidalcycles/Dirt-Samples/master')
setcps(0.6)
s("breaks125").striate(4).fast(2)
    -->
  </strudel-repl>
</div>

## Speed & direction

<div class="strudel-embed">
  <div class="embed-label">
    <span>varying playback speed/direction per cycle</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
samples('github:tidalcycles/Dirt-Samples/master')
setcps(0.6)
s("breaks125").chop(8)
  .speed("<1 -1 0.5 -0.5>")
    -->
  </strudel-repl>
</div>

## Tips

- `.chop(n)` cuts a sample into n equal pieces and plays them in order — good starting point before reordering.
- `.striate(n)` instead interleaves slices across repetitions, which tends to sound more "stuttered."
- Negative `.speed()` values play a slice backwards — combine with `.chop()` for classic jungle-style reversed hits.
