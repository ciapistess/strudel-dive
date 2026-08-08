# Strudel Dive

A Jekyll site of examples and techniques for the [Strudel](https://strudel.cc)
live coding platform, organized by genre, published via GitHub Pages.

The whole website (both content and web structure) is developed via AI assistants (Claude so far), 
so its truthfulness should always be verified.

## Structure

```
_config.yml         site config — set url/baseurl here before first publish
_data/
  genres.yml         genre list -> powers homepage grid + /genres/ index + nav
  techniques.yml      technique list -> powers homepage grid + /techniques/ index
_genres/*.md          one file per genre (collection, layout: genre)
_techniques/*.md      one file per technique (collection, layout: technique)
_layouts/              default / genre / technique page shells
_includes/              header, footer, cycle-bar (signature divider), strudel-embed
assets/css/style.css   all styling — design tokens at the top of the file
index.md, resources.md, about.md, genres/index.md, techniques/index.md
```

## Adding a playable example

Any page can embed a real, runnable Strudel pattern using the official
`@strudel/embed` web component (already loaded site-wide in the default layout).
Write the block directly as HTML — **do not** use a `{% capture %}` / `{% include %}`
combo for this; that pattern triggers a false-positive "Nesting too deep" Liquid
error on GitHub's classic Pages build (an old Liquid/Jekyll bug, see `about.md`):

```html
<div class="strudel-embed">
  <div class="embed-label">
    <span>basic four-on-the-floor</span>
    <a href="https://strudel.cc" target="_blank" rel="noopener">open full playground &rarr;</a>
  </div>
  <strudel-repl>
    <!--
setcps(0.6)
s("bd*4, ~ cp ~ cp")
    -->
  </strudel-repl>
</div>
```

## Adding a new genre or technique page

1. Create `_genres/<slug>.md` (or `_techniques/<slug>.md`) with front matter:
   ```yaml
   ---
   title: Deep House
   slug: deep-house
   accent: pulse   # pulse | cycle | amber | violet | sky
   description: One-line summary shown in the page header.
   ---
   ```
2. Add a matching entry to `_data/genres.yml` (or `_data/techniques.yml`) so it
   shows up as a card on the homepage and index page.
3. Write prose + embedded examples in the body.

## Local development

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000.

## Publishing on GitHub Pages

1. Push this repo to GitHub.
2. In **Settings → Pages**, set the source to the `main` branch (root).
   GitHub Pages will build the Jekyll site automatically — no Actions workflow needed,
   since only allow-listed plugins (`jekyll-feed`, `jekyll-sitemap`, `jekyll-seo-tag`) are used.
3. Update `url` and `baseurl` in `_config.yml`:
   - If the repo is named `<username>.github.io`, leave `baseurl` empty and set
     `url` to `https://<username>.github.io`.
   - Otherwise, set `baseurl` to `/<repo-name>` and `url` to `https://<username>.github.io`.
4. Push again — the live site will be at the URL shown in the Pages settings.

## Updating content later

This site is designed to be updated on demand: add or edit a `.md` file,
commit, push — GitHub Pages rebuilds automatically within a minute or two.
