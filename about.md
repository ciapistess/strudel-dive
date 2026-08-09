---
layout: default
title: About
permalink: /about/
---

<div class="page-head" data-accent="violet">
  <span class="card-tag">Meta</span>
  <h1>About this site</h1>
  <p class="lede">What this is, and how it grows.</p>
</div>

{% include cycle-bar.html %}

<div class="prose" markdown="1">

Strudel Dive is a reference for making music with
[Strudel](https://strudel.cc), organized around genre studies and
general techniques rather than a top-to-bottom tutorial. Every code example
on this site is a real, playable `<strudel-repl>` embed — press play and
edit it in place.

The whole website (both content and web structure) is developed via AI assistants (Claude so far), 
so its truthfulness should always be verified.

The site is work-in-progress.

## How it's updated

This site is **updated on demand** rather than on a fixed schedule. New
genre pages, technique guides, and examples get added as content is drafted
and pushed to the repository. Each page is a plain Markdown file with a
Strudel code block or two, so adding a new page is a matter of:

1. Add a Markdown file to `_genres/` or `_techniques/` (or a keyword to `_data/genres.yml` / `_data/techniques.yml` to also add its nav card).
2. Write prose + inline `<div class="strudel-embed">...<strudel-repl>` blocks (see README) for runnable examples.
3. Commit and push — GitHub Pages rebuilds automatically.

## Stack

- **Jekyll**, built natively by GitHub Pages (no custom build step required)
- **`@strudel/embed`** web component for playable code examples
- Plain HTML/CSS, no JS framework

</div>
