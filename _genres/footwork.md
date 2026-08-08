---
title: Footwork / Juke
slug: footwork
accent: violet
description: Triplet-heavy 160bpm patterns, chopped vocal stabs, polyrhythm.
---

Footwork sits around 155–165 bpm and gets its bounce from triplet subdivisions
layered against straight 16ths, plus rapid-fire chopped vocal or sample stabs.

## Triplets against 16ths

{% capture code1 %}
setcps(1.3)
stack(
  s("bd*8"),
  s("[~ cp]*3").sound("cp"),
  s("hh*16").gain(0.4)
)
{% endcapture %}
{% include strudel-embed.html code=code1 title="triplet clap over straight kick" %}

## Chopped stab

{% capture code2 %}
setcps(1.3)
s("vocal").chop(8)
  .often(rev)
  .speed(perlin.range(0.9, 1.3))
  .gain(0.8)
{% endcapture %}
{% include strudel-embed.html code=code2 title="chopped vocal stab" %}

## Tips

- Write the triplet layer as its own pattern using square-bracket grouping,
  e.g. `[~ cp]*3`, rather than trying to force it into a 16-step grid.
- `.chop()` + `.often(rev)` is a quick way to get footwork's stuttering,
  reversed-sample feel from a single one-shot.
- Keep the kick pattern dense (8th or 16th notes) — that's what carries the tempo when the rest gets sparse.

---

*Content coming: full 160bpm juke arrangement, vocal chop libraries.*
