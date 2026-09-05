# Maritime Calculator Suite — MV PAROS

**Chief Officer calculation aid** as an installable Progressive Web App (phone + desktop).

Offline-capable · Personal use · No login · Ship-shaped app icon

![App icon](icons/icon-192.png)

> **Disclaimer:** Aid for Chief Officer calculations only. Verify results with official methods / class-approved software before commercial decisions.

---

## What’s included (everything needed for GitHub)

| File / folder | Purpose |
|---------------|---------|
| `index.html` | Full suite (all calculators) |
| `manifest.json` | PWA manifest (name, icons, standalone) |
| `sw.js` | Service worker — offline cache |
| `icons/` | Ship logo icons 72–512 px |
| `404.html` | Fallback for GitHub Pages unknown paths |
| `.nojekyll` | Tells GitHub Pages not to run Jekyll |
| `.github/workflows/pages.yml` | Auto-deploy to GitHub Pages on push |
| `LICENSE` | MIT license |
| `.gitignore` | Ignores OS/editor junk |
| `README.md` | This file |

---

## Modules

| Tab | Description |
|-----|-------------|
| Draft Survey | Initial / Intermediate / Final draft survey |
| Ballast | Ballast water calculations |
| Hatches | Hatch tools |
| Hatchwise / Max Weights / Cargo Loadable | Cargo distribution & load line zone |
| Air Draft | Air draft |
| Bunker Report / Voyage Bunker Sheet | Sounding, ullage, voyage bunker |
| Change of Draft (COD) | COD with optional Draft Survey sync |
| Chief Officer tools | Extra CO helpers |
| IMSBC Cargo Guide | IMSBC reference |
| Unit Converter | Weight / length / volume |
| Useful Formulas | Trim, FWA/DWA, squat, list, etc. |

---

## Deploy to GitHub (step by step)

### 1. Create an empty repository

1. Open **https://github.com/new**
2. Name: e.g. `maritime-calculator-suite`
3. Public (free GitHub Pages needs Public, unless you have a paid plan)
4. **Do not** tick “Add a README” / .gitignore / license
5. Create repository

### 2. Upload this project

**Option A — Web upload**

1. Unzip this package
2. On the empty repo → **uploading an existing file**
3. Drag **all** files and folders listed in the table above
4. Commit

**Option B — Git CLI**

```bash
cd maritime-calculator-suite
git init
git add .
git commit -m "Initial commit: Maritime Calculator Suite PWA"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/maritime-calculator-suite.git
git push -u origin main
```

### 3. Turn on GitHub Pages

**Method A — GitHub Actions (recommended, uses `pages.yml`)**

1. Repo → **Settings** → **Pages**
2. **Source:** GitHub Actions
3. Push to `main` (or re-run the workflow under **Actions**)
4. Wait until the workflow is green

**Method B — Branch deploy (simple)**

1. Repo → **Settings** → **Pages**
2. **Source:** Deploy from a branch
3. Branch: `main` / folder `/ (root)` → Save

### 4. Open your live app

```
https://YOUR_USERNAME.github.io/maritime-calculator-suite/
```

Replace with your username and repo name. HTTPS is automatic — required for install + offline.

---

## Install on phone / desktop

1. Open the **live Pages URL** (not a local file)
2. **Android / Chrome / Edge:** menu → **Install app**, or **📲 Install App** in the suite toolbar
3. **iPhone / iPad (Safari):** Share → **Add to Home Screen**

After install, the app opens fullscreen and works **offline**.

---

## Local test (before / without GitHub)

```bash
cd maritime-calculator-suite
python3 -m http.server 8080
```

Open **http://localhost:8080**  
(`file://` cannot register a service worker or show install prompts.)

---

## Save calculator data

Use **💾 Save All** / **📂 Load Last** in the top bar.  
Optionally download JSON so you can restore after clearing browser storage.

---

## Update the app later

1. Edit files locally
2. Commit and push to `main`
3. Pages redeploys automatically (Actions) or within a minute (branch deploy)
4. If the service worker cache sticks, bump `CACHE_NAME` in `sw.js` (e.g. `marcalc-suite-v3`)

---

## License

MIT — see [LICENSE](LICENSE). Personal / onboard reference use. Not a substitute for approved loading computers or statutory calculations.
