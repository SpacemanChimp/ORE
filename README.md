# EVE Ore/Ice Harvesting Rate Calculator (Static Site)

A simple, static (GitHub Pages-friendly) calculator for:

- Harvesting totals from **m³ per cycle** + **cycle time (seconds)** + **duration (minutes)** (rounded down to full cycles)
- Output value in **raw ore/ice** and **reprocessed materials**
- Pricing at **Jita IV - Moon 4 - Caldari Navy Assembly Plant** (station `60003760`)

## Data sources

- Type + reprocessing materials: EVE Ref Reference Data  
  `https://ref-data.everef.net/types/{type_id}` (uses `type_materials`)
- Prices:
  - Fast: Fuzzwork Market aggregates  
    `https://market.fuzzwork.co.uk/aggregates/?station=60003760&types=...`
  - Slow (optional): Official ESI region orders paging (The Forge `10000002`)  
    `https://esi.evetech.net/latest/markets/10000002/orders/?order_type=sell&type_id=...`

## Host on GitHub Pages

1. Create a new GitHub repo (e.g. `eve-harvest-calculator`).
2. Upload these files to the repo root:
   - `index.html`
   - `style.css`
   - `app.js`
3. In GitHub:
   - **Settings → Pages**
   - “Build and deployment” → **Deploy from a branch**
   - Branch: `main` (or `master`) • Folder: `/ (root)`
4. Open the Pages URL GitHub provides.

## Local dev

CORS means you should run a local server rather than opening the HTML file directly:

```bash
python -m http.server 8080
```

Then open: http://localhost:8080
