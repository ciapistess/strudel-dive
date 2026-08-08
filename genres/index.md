---
layout: default
title: Genres
permalink: /genres/
---

<div class="page-head">
  <span class="card-tag">Index</span>
  <h1>Genres</h1>
  <p class="lede">Each genre page walks through the rhythmic and harmonic habits of a style, with runnable Strudel patterns you can tweak in place.</p>
</div>

{% include cycle-bar.html %}

<div class="grid">
  {% for g in site.data.genres %}
  <a class="card" href="{{ site.baseurl }}/genres/{{ g.slug }}/" data-accent="{{ g.accent }}">
    <span class="card-tag">{{ g.name }}</span>
    <p>{{ g.blurb }}</p>
  </a>
  {% endfor %}
</div>
