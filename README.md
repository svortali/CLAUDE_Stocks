# Stock Research

A simple research site for tracking high-conviction investment areas and stock picks. Hosted on GitHub Pages at **https://svortali.github.io/CLAUDE_Stocks/**.

---

## How to update content

### Update a sector's conviction signal

Open `_sectors/<sector>.md` and change the `signal` field in the front matter:

```yaml
signal: green    # green | yellow | red
```

Also update `priority` to control home-page sort order:
- `1–2` = green (high conviction)
- `3–4` = yellow (monitor)
- `5+`  = red (avoid)

### Update a stock's signal

In the stocks table, change the emoji in the Signal column:

```markdown
| NVDA | NVIDIA | 🟢 | ... |   ← high conviction
| INTC | Intel  | 🟡 | ... |   ← monitor
| QCOM | Qualcomm | 🔴 | ... | ← avoid
```

### Add a new stock to a sector

Append a row to the stocks table in the relevant `_sectors/<sector>.md`:

```markdown
| TICK | Company Name | 🟢 | One-line thesis | Any notes |
```

### Add a new sector

1. Create `_sectors/<name>.md` using this template:

```yaml
---
title: Your Sector Title
signal: green
priority: 5
headline: "One compelling sentence about why this sector matters now"
updated: YYYY-MM-DD
top_picks:
  - { ticker: XXX, signal: green }
  - { ticker: YYY, signal: yellow }
---

## Why Now

- Bullet point macro thesis

## Key Risks

- Bullet point risk

## Catalysts to Watch

- What to watch for

## Stocks

| Ticker | Company | Signal | Thesis | Notes |
|--------|---------|--------|--------|-------|
| XXX | Company | 🟢 | Thesis here | Notes here |
```

2. Push to `main` — GitHub Pages rebuilds automatically within ~2 minutes.

### Update the "Last Updated" date on the dashboard

Edit `index.md` and change the date in the header:

```markdown
<span class="as-of">Updated May 2026</span>
```

---

## Site structure

```
_sectors/           ← one .md file per investment sector
_layouts/           ← page templates (don't edit unless redesigning)
_includes/          ← reusable HTML components
assets/css/         ← styles (don't edit unless redesigning)
index.md            ← home dashboard
_config.yml         ← Jekyll site config
```

## Deploying

Push any changes to the `main` branch. GitHub Pages rebuilds automatically.

To enable GitHub Pages for the first time:
1. Go to the repo → **Settings** → **Pages**
2. Source: **Deploy from a branch** → `main` branch → `/ (root)`
3. Save — the site will be live at `https://svortali.github.io/CLAUDE_Stocks/`
