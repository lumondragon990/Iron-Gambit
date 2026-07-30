# Iron Gambit

Luxury training apparel out of Houston, TX. Chess builds the plan, iron builds the body.

**Give up the piece. Take the board.**

Static site — no build step, no dependencies to install, no framework. Three HTML files.

---

## Files

| File | What it is |
|---|---|
| `index.html` | The whole site. Hero, creed, Royal Series grid, lookbook, Houston, drop-list capture. |
| `assets/` | Logo in gold, cream and dark, plus the favicon. |
| `docs/BRAND.md` | Brand core. Also lives in the agents repo. |
| `docs/LAUNCH-PLAN.md` | 90-day launch plan. |
| `docs/AI-AGENTS.md` | The agent prompts, for reference. |

The AI agents run in a **separate repo on Railway** (`iron-gambit-agents`) and are not part of this site.

---

## Deploy to Vercel

1. Create a new GitHub repo (e.g. `iron-gambit`) and push these files to the root.
2. Go to [vercel.com](https://vercel.com) → **Add New** → **Project** → import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. **Deploy.**

That's it. `vercel.json` turns on clean URLs and adds a couple of security headers.

**Custom domain:** Project → Settings → Domains → add `irongambit.com`, then point your registrar's nameservers or add the A/CNAME records Vercel shows you.

### Local preview

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

## Before you go live

**1. Set the drop date.** In `index.html`, find:

```js
var TARGET = new Date('2026-09-12T19:00:00-05:00').getTime();
```

**2. Wire up the email form.** In `index.html`, find `/* TODO: POST to your email provider */`. Right now the form validates the address and shows a confirmation but stores nothing. Drop your Klaviyo or Shopify endpoint there.

**3. Logo.** Already done — the real mark is vector-traced into one inline `<symbol id="crest">` block and filled with `currentColor`, so it goes gold on dark and dark on cream automatically. If you ever get a cleaner vector from a designer, replace the single `<path d="...">` inside that symbol and all nine instances update.

**4. Add product photos.** The Royal Series cards use colored panels with the crest as placeholders. Replace the `.shot` divs with `<img>` tags.

**5. Replace the lookbook tiles.** Six square slots under "Shot in the Iron House."

---

## Palette

```
Obsidian          #0A0908
Burgundy Reserve  #5E1D25
Sandstone Beige   #B9A488
Cream             #F2EBDD
Gold              #D8B678
```

Type: Cormorant Garamond (display), Jost (body), JetBrains Mono (data).

---

© 2026 Iron Gambit · Houston, Texas
