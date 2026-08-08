---
title: Pattern Basics
slug: pattern-basics
accent: cycle
description: Mini-notation, sequences, cycles — the grammar of Strudel patterns.
---

Everything in Strudel happens inside a **cycle** — one repeating unit of time.
Mini-notation (the stuff inside quotes) describes how events are spaced
within that cycle.

## The core symbols

<div class="strudel-embed">
  <div class="embed-label">
    <span>four evenly-spaced steps</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
s("bd sn bd sn")
    -->
  </strudel-repl>
</div>

- `~` — a rest (silence for that step)
- `*n` — repeat a step n times, e.g. `bd*4`
- `[ ]` — group steps to subdivide a slot, e.g. `bd [sn sn]`
- `< >` — alternate one value per cycle, e.g. `<bd sn>`
- `,` inside a pattern — layer patterns in parallel

## Alternation across cycles

<div class="strudel-embed">
  <div class="embed-label">
    <span>a different note each cycle</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
n("<0 2 4 7>").scale("C major").s("piano")
    -->
  </strudel-repl>
</div>

## Stacking patterns

Use `stack(...)` to layer multiple independent patterns that all play together.

<div class="strudel-embed">
  <div class="embed-label">
    <span>stacked drum layers</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
stack(
  s("bd*4"),
  s("~ cp ~ cp"),
  s("hh*8").gain(0.5)
)
    -->
  </strudel-repl>
</div>

## Tips

- Read mini-notation left to right as "what happens in this slice of the cycle," not as absolute time.
- Nesting brackets is the main way to add rhythmic detail without changing the overall tempo.
- `setcps(n)` sets cycles-per-second — lower it to slow the whole pattern down for testing.
