---
layout: default
title: Resources
permalink: /resources/
---

<div class="page-head" data-accent="sky">
  <span class="card-tag">Reference</span>
  <h1>Resources</h1>
  <p class="lede">Official docs, community spaces, and tools worth bookmarking alongside this site.</p>
</div>

{% include cycle-bar.html %}

<div class="prose">

## Official

- [strudel.cc](https://strudel.cc) — the live playground itself
- [Strudel documentation](https://strudel.cc/learn/) — official learn/reference docs
- [Strudel source (Codeberg)](https://codeberg.org/uzu/strudel) — source code, issues, discussion
- [@strudel/embed](https://www.npmjs.com/package/@strudel/embed) — the web component used for the playable examples on this site

## Related projects

- [Tidal Cycles](https://tidalcycles.org) — the Haskell live-coding language Strudel is ported from
- [TOPLAP](https://toplap.org) — the live coding / algorave community umbrella

## Sample banks & sound sources

- Strudel ships with General MIDI instruments (`gm_*`) and drum machine banks (`.bank("RolandTR909")` etc.) — no external samples required to get started.
- Custom samples can be loaded with `samples()` pointing at a URL or local set — see the official docs for the current syntax.

</div>
