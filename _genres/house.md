---
title: House
slug: house
accent: pulse
description: Four-on-the-floor grooves, swung hats, filtered chords.
---

House runs on a steady kick on every beat, a clap or snare on 2 and 4, and hats
that carry the swing. Most of the character comes from how you filter and
automate chords over that base.

## The floor

Kick on every quarter note, clap on the backbeat, offbeat hats.

{% capture code1 %}
setcps(0.5)
stack(
  s("bd*4"),
  s("~ cp ~ cp"),
  s("hh*8").gain(0.5).pan(sine.range(0.3, 0.7))
)
{% endcapture %}
{% include strudel-embed.html code=code1 title="basic house floor" %}

## Filtered chords

Automate a lowpass filter with a slow sine or saw wave to get the classic
"opening up" feel over a bar or a phrase.

{% capture code2 %}
setcps(0.5)
n("<0 3 5 3>").chord("major7")
  .s("gm_epiano1")
  .lpf(sine.range(300, 3000).slow(8))
  .room(0.4)
{% endcapture %}
{% include strudel-embed.html code=code2 title="filtered chord stab" %}

## Tips

- Keep the kick pattern dead simple — `bd*4` — and put the groove in the hats and percussion instead.
- Swing the hats slightly with `.swingBy(1/3, 8)` for a more human feel.
- Sidechain-style pumping can be faked with `.gain(sine.range(0.6,1).fast(2))` synced to the kick.

---

*Content coming: garage-influenced house, deep house pads, vocal chops.*
