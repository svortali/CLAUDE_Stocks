# Stock Research

Investment research site for tracking high-conviction sectors and stocks.
Live at: **https://claude-stocks.vercel.app** (or your Vercel URL)

Open locally with VS Code Live Server — just right-click `index.html` → *Open with Live Server*.

---

## File structure

```
index.html                  ← Home dashboard (sector cards)
sectors/
  semiconductors.html       ← Sector detail pages
  space.html
  ai-software.html
  defense-cyber.html
assets/css/style.css        ← All styles
```

---

## How to update

### Change a sector's conviction signal (home page card color)

Open `index.html`. Find the sector card and change the CSS class on the `<a>` tag:

```html
<a href="sectors/semiconductors.html" class="sector-card green">   ← green | yellow | red
```

Also update the `signal-dot` class inside to match:
```html
<div class="signal-dot green"></div>
```

### Change a stock's signal badge

Open the sector's `.html` file (e.g. `sectors/semiconductors.html`).
Find the stock row and change the badge class and text:

```html
<span class="badge green">Buy</span>     ← green/Buy
<span class="badge yellow">Watch</span>  ← yellow/Watch
<span class="badge red">Avoid</span>     ← red/Avoid
```

### Add a new stock row

Find the `<tbody>` in the stocks table and add a row:

```html
<tr>
  <td>TICK</td>
  <td>Company Name</td>
  <td><span class="badge green">Buy</span></td>
  <td>One-line thesis</td>
  <td>Supporting notes</td>
</tr>
```

### Add a new sector

1. Copy any sector file, e.g. `cp sectors/space.html sectors/biotech.html`
2. Edit the title, headline, signal badge, and content
3. Add a card to `index.html` (copy an existing card block and update links/text)
4. Add a nav link in every HTML file's `<nav>` block

---

## Deploying

Push to `main` — Vercel deploys automatically.
