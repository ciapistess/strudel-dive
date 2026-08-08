---
layout: default
title: Techniques
permalink: /techniques/
---

<div class="page-head">
  <span class="card-tag">Index</span>
  <h1>Techniques</h1>
  <p class="lede">General-purpose Strudel skills that apply across genres — pattern grammar, sequencing, sound design, and generative control.</p>
</div>

{% include cycle-bar.html %}

<div class="grid">
  {% for t in site.data.techniques %}
  <a class="card" href="{{ site.baseurl }}/techniques/{{ t.slug }}/" data-accent="{{ t.accent }}">
    <span class="card-tag">{{ t.name }}</span>
    <p>{{ t.blurb }}</p>
  </a>
  {% endfor %}
</div>
