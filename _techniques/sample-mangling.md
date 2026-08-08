---
title: Sample Mangling
slug: sample-mangling
accent: violet
description: Slicing, chopping, and manipulating samples in Strudel.
---

Strudel can slice a single sample into pieces and reorder, reverse, or
re-trigger them — the basis of breakbeat chopping and glitch textures.

## Chopping

{% capture code1 %}
setcps(0.6)
s("break").chop(8)
{% endcapture %}
{% include strudel-embed.html code=code1 title="chop a break into 8 pieces" %}

## Reordering with striate

{% capture code2 %}
setcps(0.6)
s("break").striate(4).fast(2)
{% endcapture %}
{% include strudel-embed.html code=code2 title="striate interleaves slices" %}

## Speed & direction

{% capture code3 %}
setcps(0.6)
s("break").chop(8)
  .speed("<1 -1 0.5 -0.5>")
{% endcapture %}
{% include strudel-embed.html code=code3 title="varying playback speed/direction per cycle" %}

## Tips

- `.chop(n)` cuts a sample into n equal pieces and plays them in order — good starting point before reordering.
- `.striate(n)` instead interleaves slices across repetitions, which tends to sound more "stuttered."
- Negative `.speed()` values play a slice backwards — combine with `.chop()` for classic jungle-style reversed hits.
