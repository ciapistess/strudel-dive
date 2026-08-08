---
title: Randomness & Generative Control
slug: randomness
accent: sky
description: sometimes, degradeBy, perlin, and other sources of controlled chaos.
---

Strudel has several built-in sources of randomness that stay musically
useful because they're deterministic per-cycle rather than fully chaotic.

## Thinning a pattern

{% capture code1 %}
setcps(0.6)
s("hh*16").degradeBy(0.5)
{% endcapture %}
{% include strudel-embed.html code=code1 title="degradeBy removes events probabilistically" %}

## Random note choice

{% capture code2 %}
setcps(0.6)
n(irand(8)).scale("C minor").s("piano")
{% endcapture %}
{% include strudel-embed.html code=code2 title="irand picks a random integer each step" %}

## Smooth random motion

{% capture code3 %}
setcps(0.6)
n("0 3 5 7").s("sawtooth")
  .lpf(perlin.range(200, 4000).slow(4))
{% endcapture %}
{% include strudel-embed.html code=code3 title="perlin noise for organic modulation" %}

## Tips

- `.degradeBy(x)` and `.sometimesBy(x, fn)` both take a probability 0–1 — start subtle (0.1–0.3) unless you want heavy variation.
- `irand(n)` gives a hard-edged random integer; `perlin` gives smooth continuous randomness — pick based on whether you want steps or drift.
- Because Strudel's randomness is seeded by cycle count, patterns stay reproducible when you share code, unlike true random noise.
