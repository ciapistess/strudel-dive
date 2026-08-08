---
title: Techno
slug: techno
accent: cycle
description: Driving loops, hypnotic repetition, minimal variation over long cycles.
---

Techno is about a groove that barely changes and a handful of elements that
shift almost imperceptibly over many cycles. In Strudel, that means leaning
on slow-moving modulation (`.slow()`, long `sine`/`perlin` ranges) rather than
writing lots of distinct sections.

## The loop

<div class="strudel-embed">
  <div class="embed-label">
    <span>techno loop base</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.55)
stack(
  s("bd*4"),
  s("~ ~ rim ~").gain(0.8),
  s("hh*16").gain(perlin.range(0.2, 0.5))
)
    -->
  </strudel-repl>
</div>

## Slow-evolving stab

<div class="strudel-embed">
  <div class="embed-label">
    <span>euclidean stab with slow filter drift</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.55)
n("0")
  .s("sawtooth")
  .lpf(perlin.range(200, 4000).slow(16))
  .resonance(8)
  .struct("t(5,8)")
    -->
  </strudel-repl>
</div>

## Tips

- Euclidean rhythms (`t(5,8)`, `t(3,8)`) are a fast way to get techno's
  off-kilter percussion without hand-writing every hit.
- Use `.slow(n)` on modulation sources so changes happen over many bars, not one.
- A single well-automated filter often does more work than adding new layers.

---

*Content coming: acid techno with `.cutoff`/`.resonance` sweeps, hard techno kick design.*
