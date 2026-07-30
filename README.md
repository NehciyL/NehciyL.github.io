# Site setup

## Run it locally

```bash
cd site
quarto preview
```

Opens at `localhost:4200` and live-reloads as you edit. Leave it running
while you write.

## Files

| File | What it does |
|---|---|
| `_quarto.yml` | Site config: title, nav, links. Edit name, email, Scholar ID. |
| `theme.scss` | All styling. Palette and type live at the top under `scss:defaults`. |
| `header.html` | Loads the three fonts. |
| `index.qmd` | Homepage. |
| `research.qmd` | Paper list. |

Add `profile.jpg` and a `papers/` folder alongside these. `cv.pdf` goes in
the same directory.

## Palette

Defined at the top of `theme.scss`:

- ink `#1a1d1f` — near-black, slightly cool
- paper `#fdfdfc` — off-white, not cream
- muted `#6b7075` — metadata and labels
- rule `#e3e3de` — hairlines
- ledger `#2f5d50` — deep green, used only for links and the active status label

## Type

- Newsreader — name and paper titles
- Source Serif 4 — body prose, designed for screen reading
- IBM Plex Sans — nav, status labels, metadata

## Adding a paper

Copy a `.paper` block in `research.qmd`. To change status, edit the text in
`.paper-status` — add `.current` to that div to tint it green. Status ladder:
In preparation → Working paper → R&R at [Journal] → Forthcoming → Published.

## Deploy

```bash
quarto publish gh-pages
```

Or push `_site/` to Cloudflare Pages. Point your domain at it in DNS.

Add a `.gitignore` containing `_site/` and `.quarto/` before the first
commit — and keep CRSP or Compustat extracts out of the repo entirely.
