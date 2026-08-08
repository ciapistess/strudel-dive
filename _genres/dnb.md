---
title: Drum & Bass
slug: dnb
accent: amber
description: Fast breaks, chopped amens, sub-bass, syncopated snares.
---

DnB lives around 160–175 bpm with the groove concentrated in the break, not
the kick. In Strudel, set a fast `setcps` and build the break as its own
pattern you can chop independently from the bass.

## The break

{% capture code1 %}
setcps(1.4)
s("bd ~ sn ~ ~ bd sn ~")
  .bank("RolandTR909")
{% endcapture %}
{% include strudel-embed.html code=code1 title="basic broken beat" %}

## Sub-bass under the break

{% capture code2 %}
setcps(1.4)
n("<0 0 3 0>").s("sawtooth")
  .lpf(200)
  .note(-24)
  .gain(0.9)
{% endcapture %}
{% include strudel-embed.html code=code2 title="reese-ish sub bass" %}

## Tips

- Chop a sample into 16ths with `.chop(16)` and reorder with `.striate()` or
  pattern strings to build amen-style breaks quickly.
- Keep the sub monophonic and simple — DnB low end works best with one clear
  note at a time, not chords.
- Automate `.crush()` or `.distort()` sparingly on the break to add grit without losing punch.

---

*Content coming: liquid DnB pads, jump-up bass design, half-time reinterpretation.*
