# manchanda.co.uk

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
about page, and the MoSP blurb and summary are all in `_config.yml`. Each
contact has an obfuscated `address` for display and a real `mailto`, so the
address shown is not the one in the link. Talks and posters go in
`_data/presentations.yml`, teaching in `_data/teaching.yml` — each section
shows a placeholder pointing at its file while that file is empty.

The whole design is one plain stylesheet, `assets/css/main.css` — there is no
Sass build step. The Leviathan plum carries the masthead on every page and the
whole MoSP panel; gold is reserved for what sits on the plum, for rules, and
for the bibliography numbering.

## Moving to manchanda.co.uk — parked, not active

The site is currently served from the GitHub Pages project path. Everything for
the custom domain is in the repo but switched off, so pushing can't break the
live site:

- `CNAME.disabled` holds the domain. Pages only reads a file named exactly
  `CNAME`, so while it is renamed nothing happens.
- `_config.yml` has the project-path `url` and `baseurl` active, with the
  custom-domain pair commented out directly beneath them.

Do the DNS work first, then flip both in one commit and push.

### 1. Move mail off the apex — do this before anything else

Mail is the part that can actually break, and it is not enough to leave the MX
record alone. The current records are:

```
MX   manchanda.co.uk.  ->  0 manchanda.co.uk.
A    manchanda.co.uk.  ->  185.53.172.126        (Hosting UK, 01.mag.hostinguk.net)
TXT  v=spf1 ip4:185.53.172.126 ... +a +mx ~all
```

The MX points at the apex hostname itself. Repointing that hostname's A records
at GitHub therefore redirects mail to GitHub's web servers, and mail to
ganga@manchanda.co.uk starts bouncing. Give mail its own name first:

1. Add an `A` record `mail` -> `185.53.172.126`. Better still, ask Hosting UK
   for their documented mail hostname and use that — a shared IP can be
   renumbered without warning.
2. Change the `MX` record to `0 mail.manchanda.co.uk.`
3. Send yourself a test message and confirm it arrives.

Only once mail is arriving on its own hostname should the apex move.

### 2. Point the apex and www at GitHub

Four `A` records on `@`:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Four `AAAA` records on `@`, for IPv6:

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

`www` is currently a CNAME to the apex, which will follow it to GitHub on its
own. To be explicit, point it at `gangasm.github.io` — the Pages host, not the
custom domain. GitHub then redirects www to the apex.

Check propagation before going further:

```sh
dig +short manchanda.co.uk          # the four GitHub IPs
dig +short www.manchanda.co.uk      # gangasm.github.io
dig +short MX manchanda.co.uk       # mail.manchanda.co.uk
```

### 3. Tidy the SPF record

Once the apex points at GitHub, the `+a` mechanism authorises GitHub's IPs to
send mail as the domain. Drop `+a` from the TXT record; `+mx` will resolve to
the new mail hostname and can stay.

### 4. Flip the repository

```sh
git mv CNAME.disabled CNAME
```

and in `_config.yml` swap the active `url`/`baseurl` pair for the commented one,
so the site sits at the domain root. Commit and push together.

### 5. Finish in GitHub

Settings -> Pages -> Custom domain -> `manchanda.co.uk` -> Save. The `CNAME`
file usually fills this in by itself; check that it did. Then wait for the
Let's Encrypt certificate and tick **Enforce HTTPS** — it stays greyed out until
the certificate is issued, normally minutes, occasionally up to 24 hours.

Article permalinks do not change when the domain does, so old `/mosp/<title>/`
links keep working through GitHub's redirect from the project path.

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

`assets/images/portrait.jpg` is a square 1000px crop, pointed at by `portrait:` in
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

Then open <http://localhost:4000/>.

Pushing to `main` is enough to publish; GitHub Pages builds the site itself.
Until the custom domain is switched on it serves from the project path above.
