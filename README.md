# gangasm.github.io/Meditations-on-Second-Philosophy

Personal site of Ganga Singh Manchanda, built with Jekyll and served by GitHub Pages.

## Structure

| Page     | Source          | URL          |
| -------- | --------------- | ------------ |
| About me | `index.html`    | `/`          |
| Research | `research.html` | `/research/` |
| MoSP     | `mosp.html`     | `/mosp/`     |
| Articles | `_posts/`       | `/mosp/<title>/` |

Navigation lives in `_data/nav.yml`; the current page is marked with Dirac
notation (`|research⟩`). Identity, the contact addresses and link row on the
about page, and the MoSP blurb and summary are all in `_config.yml`. Contact
addresses are written out obfuscated (`[at]`, `[dot]`) and rendered as plain
text, not as `mailto:` links. Talks and posters go in
`_data/presentations.yml` — that section hides itself while the file is empty.

The whole design is one plain stylesheet, `assets/css/main.css` — there is no
Sass build step. The Leviathan plum carries the masthead on every page and the
whole MoSP panel; gold is reserved for what sits on the plum, for rules, and
for the bibliography numbering.

## Writing a post

Add a file to `_posts/` named `YYYY-MM-DD-slug.md`:

```yaml
---
title: But what IS a black hole?
subtitle: An optional one-line standfirst
venue: Submission to SoME 2025      # optional, shown beside the date
slides: /assets/slides/some.pdf     # optional, adds a "slides" link
author: Ganga Singh Manchanda
category: physics
---
```

`layout: post` is applied automatically. Work in progress goes in `_drafts/`,
which is excluded from the build; `jekyll serve --drafts` renders it locally.

MathJax loads on article pages automatically — write `$inline$` and `$$display$$`.

Put slide decks in `assets/slides/`.

## Images

`assets/images/portrait.jpg` is a 7:8 crop, pointed at by `portrait:` in
`_config.yml`; remove that key and the about page falls back to a placeholder.

`favicon.png`, `assets/images/icon-180.png` and `icon-512.png` are all the MoSP
**M**, cropped from `assets/images/mosp-mark.png`. Regenerate them from the
wordmark if it ever changes.

## Running it locally

Requires Ruby 3.1 or newer — macOS's built-in Ruby 2.6 is too old, so install a
current one first (`brew install ruby`, then put it on your `PATH`).

```sh
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/Meditations-on-Second-Philosophy/>.

Pushing to `main` is enough to publish; GitHub Pages builds the site itself.
