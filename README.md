# Iron Gambit

Luxury training apparel out of Houston, TX. Chess builds the plan, iron builds the body.

**Give up the piece. Take the board.**

Static site — no build step, no dependencies to install, no framework. Three HTML files.

---

## Files

| File | What it is |
|---|---|
| `index.html` | The storefront. Hero, creed, Royal Series grid, lookbook, Houston, drop-list capture. |
| `agents3d.html` | **Command** — a 3D city where the seven AI agents work. Enterable buildings. Needs a GPU. |
| `agents.html` | The 2D isometric version of Command. Lighter; good fallback for older phones. |
| `docs/BRAND.md` | Brand core. Upload this to every agent Project. |
| `docs/LAUNCH-PLAN.md` | 90-day launch plan. |
| `docs/AI-AGENTS.md` | The seven agent prompts. |

---

## Deploy to Vercel

1. Create a new GitHub repo (e.g. `iron-gambit`) and push these files to the root.
2. Go to [vercel.com](https://vercel.com) → **Add New** → **Project** → import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. **Deploy.**

That's it. `vercel.json` turns on clean URLs, so Command lives at `/agents3d` (no `.html`).

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

**3. Swap in the real logo.** Both pages pull from one inline `<symbol id="crest">` block. Replace it once per file and every instance updates. Export your logo as SVG with the fill set to `#D8B678`.

**4. Add product photos.** The Royal Series cards use colored panels with the crest as placeholders. Replace the `.shot` divs with `<img>` tags.

**5. Replace the lookbook tiles.** Six square slots under "Shot in the Iron House."

---

## Notes on Command

`agents3d.html` loads three.js from `cdnjs.cloudflare.com`. It needs an internet connection and a WebGL-capable browser. If the engine fails to load, the page shows a message instead of failing silently.

The agents are a **simulation** — scripted movement and task logs, not seven live Claude instances. It's a dashboard for the real system, which runs in Claude Projects using the prompts in `docs/AI-AGENTS.md`. Making it genuinely live means a backend on Railway writing real events to a database, with this page reading from it.

Controls: drag to orbit, right-drag or shift-drag to pan, scroll to zoom, click a building to go inside.

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
