---
title: Footwork / Juke
slug: footwork
accent: violet
description: Triplet-heavy 160bpm patterns, chopped vocal stabs, polyrhythm.
---

Footwork sits around 155–165 bpm and gets its bounce from triplet subdivisions
layered against straight 16ths, plus rapid-fire chopped vocal or sample stabs.

## Triplets against 16ths

<div class="strudel-embed">
  <div class="embed-label">
    <span>triplet clap over straight kick</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(1.3)
stack(
  s("bd*8"),
  s("[~ cp]*3").sound("cp"),
  s("hh*16").gain(0.4)
)
    -->
  </strudel-repl>
</div>

## Chopped stab

Footwork stabs are traditionally vocal chops, but "vocal" isn't a sample
Strudel ships by default — you'd load your own with `samples(...)`. The
example below stands in with a loaded break sample so it's playable as-is;
swap the `samples(...)` line for your own vocal/foley source.

<div class="strudel-embed">
  <div class="embed-label">
    <span>chopped sample stab</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
samples('github:tidalcycles/Dirt-Samples/master')
setcps(1.3)
s("breaks125").chop(8)
  .often(rev)
  .speed(perlin.range(0.9, 1.3))
  .gain(0.8)
    -->
  </strudel-repl>
</div>

## Tips

- Write the triplet layer as its own pattern using square-bracket grouping,
  e.g. `[~ cp]*3`, rather than trying to force it into a 16-step grid.
- `.chop()` + `.often(rev)` is a quick way to get footwork's stuttering,
  reversed-sample feel from a single one-shot.
- Keep the kick pattern dense (8th or 16th notes) — that's what carries the tempo when the rest gets sparse.

---

*Content coming: full 160bpm juke arrangement, vocal chop libraries.*
