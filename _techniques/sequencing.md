---
title: Sequencing & Structure
slug: sequencing
accent: pulse
description: Arranging patterns over time — song mode, arrangement, conditionals.
---

Beyond a single loop, Strudel gives you ways to change what plays over
longer spans — introducing elements, dropping others out, and reacting
conditionally cycle to cycle.

## Changing patterns over cycles with `<>`

{% capture code1 %}
setcps(0.6)
s("<[bd*4] [bd*4, cp*2] [bd*4, cp*2, hh*8]>")
{% endcapture %}
{% include strudel-embed.html code=code1 title="build-up over three cycles" %}

## Conditional layers

{% capture code2 %}
setcps(0.6)
stack(
  s("bd*4"),
  s("cp*2").sometimesBy(0.5, fast(2))
)
{% endcapture %}
{% include strudel-embed.html code=code2 title="sometimesBy for variation" %}

## Tips

- `<a b c>` cycling through whole sub-patterns is the simplest way to write an arrangement without external tooling.
- `.sometimesBy(prob, fn)`, `.often(fn)`, `.rarely(fn)` apply a transformation
  to only a fraction of events — great for keeping loops from feeling static.
- Keep a "base" stack of always-on elements separate from layers you toggle, so the core groove never breaks.
