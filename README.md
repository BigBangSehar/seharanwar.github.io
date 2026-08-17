# seharanwar.github.io

Personal developer portfolio for Sehar Anwar — BS Physics, UET Lahore.
Pure HTML/CSS/JS, no build step, ready for GitHub Pages.

## Files
- `index.html` — the whole site (single page)
- `favicon.svg`
- `Sehar Anwar RESUME.pdf` — downloadable resume
- `robots.txt`
- `sitemap.xml`

## 1. Before publishing
- Confirm the GitHub (`github.com/seharanwar`) and LinkedIn (`linkedin.com/in/sehar-anwar-82b981427`) URLs are correct.
- Optional: add a `og-image.png` (1200×630) to the repo root for nicer link previews — the meta tags already point to it.

## 2. Deploy to GitHub Pages

```bash
# from inside this folder
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/seharanwar/seharanwar.github.io.git
git push -u origin main
```

Because the repo is named `<username>.github.io`, GitHub Pages serves it
automatically from the `main` branch root — no extra config needed. Give it
1–2 minutes, then visit **https://seharanwar.github.io**.

If Pages isn't enabled yet: repo **Settings → Pages → Build and deployment
→ Source: Deploy from a branch → Branch: main / (root)**.

## 3. Run the Lighthouse SEO audit

**Option A — Chrome DevTools (easiest)**
1. Open `https://seharanwar.github.io` in Chrome.
2. Open DevTools (F12 / Cmd+Opt+I) → **Lighthouse** tab.
3. Categories: check **SEO** (and any others you want). Device: Mobile.
4. Click **Analyze page load**.

**Option B — CLI**
```bash
npm install -g lighthouse
lighthouse https://seharanwar.github.io --only-categories=seo --view
```

### What's already in place to hit ≥90 SEO
- Unique, descriptive `<title>` and meta description
- `lang="en"`, `viewport` meta, mobile-responsive layout
- Canonical URL, `robots.txt`, `sitemap.xml`
- Open Graph + Twitter Card tags
- JSON-LD `Person` structured data (name, alma mater, social links)
- Semantic HTML (`header`, `nav`, `main`, `section`, `footer`), single `<h1>`
- All links have descriptive text (no "click here") and `rel="noopener noreferrer"` on externals
- Legible font sizes (16px base) and tappable link/button targets
- No render-blocking heavy assets — fonts loaded with `preconnect` + `display=swap`, no JS frameworks

If any single point gets docked, it's almost always one of: a missing
`og-image.png`, a body-content crawlability check on a domain firewall, or a
temporary robots/meta issue — Lighthouse's SEO panel names the exact failing
audit so you can fix it directly.
