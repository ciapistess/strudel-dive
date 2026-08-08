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

{% capture code1 %}
setcps(0.55)
stack(
  s("bd*4"),
  s("~ ~ rim ~").gain(0.8),
  s("hh*16").gain(perlin.range(0.2, 0.5))
)
{% endcapture %}
{% include strudel-embed.html code=code1 title="techno loop base" %}

## Slow-evolving stab

{% capture code2 %}
setcps(0.55)
n("0")
  .s("sawtooth")
  .lpf(perlin.range(200, 4000).slow(16))
  .resonance(8)
  .struct("t(5,8)")
{% endcapture %}
{% include strudel-embed.html code=code2 title="euclidean stab with slow filter drift" %}

## Tips

- Euclidean rhythms (`t(5,8)`, `t(3,8)`) are a fast way to get techno's
  off-kilter percussion without hand-writing every hit.
- Use `.slow(n)` on modulation sources so changes happen over many bars, not one.
- A single well-automated filter often does more work than adding new layers.

---

*Content coming: acid techno with `.cutoff`/`.resonance` sweeps, hard techno kick design.*
