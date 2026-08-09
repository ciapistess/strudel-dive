---
layout: default
title: Home
---

<section class="hero">
  <div class="eyebrow">// live coding music in the browser, one cycle at a time</div>
  <h1>Field notes for making music with Strudel.</h1>
  <p class="lede">
    Strudel is a browser-based live coding environment for algorithmic music,
    a JavaScript port of Tidal Cycles. This site collects working patterns,
    genre studies, and technique guides — updated whenever there's something
    new worth writing down.
  </p>

  <div class="strudel-embed">
  <div class="embed-label">
    <span>press play — this is live</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(1)
n("<0 2 4 6>*4").scale("C:minor")
  .s("sawtooth")
  .lpf(sine.range(400, 2000).slow(4))
  .room(0.3)
  
    -->
  </strudel-repl>
</div>
</section>

{% include cycle-bar.html %}

<section>
  <p class="section-label">Browse by genre</p>
  <div class="grid">
    {% for g in site.data.genres %}
    <a class="card" href="{{ site.baseurl }}/genres/{{ g.slug }}/" data-accent="{{ g.accent }}">
      <span class="card-tag">{{ g.name }}</span>
      <p>{{ g.blurb }}</p>
    </a>
    {% endfor %}
  </div>
</section>

<section>
  <p class="section-label">Techniques</p>
  <div class="grid">
    {% for t in site.data.techniques %}
    <a class="card" href="{{ site.baseurl }}/techniques/{{ t.slug }}/" data-accent="{{ t.accent }}">
      <span class="card-tag">{{ t.name }}</span>
      <p>{{ t.blurb }}</p>
    </a>
    {% endfor %}
  </div>
</section>

<section>
  <p class="section-label">Other useful information</p>
  <div class="grid">
    <a class="card" href="{{ site.baseurl }}/resources/" data-accent="sky">
      <span class="card-tag">Resources</span>
      <p>Official docs, community links, sample banks, and tools worth knowing about.</p>
    </a>
    <a class="card" href="{{ site.baseurl }}/about/" data-accent="violet">
      <span class="card-tag">About</span>
      <p>What this site is, how it's maintained, and how content gets added.</p>
    </a>
  </div>
</section>
