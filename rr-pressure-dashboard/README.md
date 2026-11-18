# Pressure Index: SupeRR Selector S2 analyst dashboard

A static, dependency-free dashboard (HTML, CSS, vanilla JS). No build step, no server code.

## Run locally
Open `index.html` in a browser, or serve the folder: `python3 -m http.server 8080`.

## Deploy (free, about two minutes)
- **Netlify:** drag the folder onto app.netlify.com/drop. `netlify.toml` is included.
- **Vercel:** `npx vercel --prod` inside the folder. `vercel.json` is included.
- **GitHub Pages:** push the folder to a repo, then Settings > Pages > deploy from the main branch root.
- **Cloudflare Pages:** create a project, upload the folder, leave the build command empty.

## Structure
- `index.html`: page shell and navigation.
- `assets/styles.css`, `assets/app.js`: styling and views (Overview, Batters, Bowlers, Compare, Method).
- `data/players.js`: all results (`window.RRDATA`), generated from the supplied CSVs.

## Updating the data
Re-run the analysis pipeline and overwrite `data/players.js` with the same structure. Player fields: rk rank, rt rating, pv pressure value, ov usual value, np weighted pressure balls, no ordinary balls, ps positive spells %, p10 bootstrap P(top 10), mr mean rank, pt pattern (Riser, Steady, Dipper), sp/su strike rate or economy under pressure/usual, bp boundary or dot %, dp/du dismissals or wickets per 100, ip IPL share %, se standard error.
