# Yuliyan Nikolaev — Portfolio

A single-page static portfolio (People Lead, SAP Commerce Cloud Operations).
No build step, no framework — plain HTML/CSS/JS, deployable to Vercel as a static site.

## Structure

```
.
├── index.html                          # the site (all CSS + JS inline)
├── favicon.svg                         # monogram favicon
├── robots.txt
├── vercel.json                         # caching + security headers
├── assets/
│   └── yuliyan-nikolaev-portrait.jpg   # hero portrait
├── DESIGN-HANDOFF.md                   # OpenDesign export notes (not deployed)
├── DESIGN-MANIFEST.json                # OpenDesign export notes (not deployed)
├── Portrait.png                        # source asset (not deployed)
└── Yuliyan_Nikolaev_CV.docx            # source CV (not deployed)
```

`.vercelignore` keeps the OpenDesign export notes, source assets, and this README
out of the deployment so only the site is published.

## Deploy to Vercel

### Option A — Vercel CLI (fastest)

```bash
npx vercel        # first run: follow the login prompt, accept defaults
npx vercel --prod # promote to your production URL
npx vercel        # preview deploys from then on
```

When asked for settings, accept the defaults: Vercel detects a static site with
`index.html` at the root. **Framework preset: Other / Vercel static**, no build
command, no output directory.

### Option B — Git + Vercel dashboard

```bash
git add -A
git commit -m "Prepare portfolio for Vercel"
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin master
```

Then in the Vercel dashboard: **Add New → Project → Import** the repo and deploy.
Leave the framework preset and build settings at their defaults.

### Option C — Drag and drop

Drop this folder onto <https://vercel.com/new> and deploy.

## After the first deploy

1. Add a custom domain in **Project → Settings → Domains**.
2. Give rich link previews real absolute URLs: in `index.html`, set `og:url`
   to `https://<your-domain>/` and update the `og:image` / `twitter:image`
   values to `https://<your-domain>/assets/yuliyan-nikolaev-portrait.jpg`, then
   redeploy. (`link rel="canonical"` can be updated the same way.)
3. Optionally link the CV: add a `Download CV` button pointing at the deployed
   `Yuliyan_Nikolaev_CV.docx` (remove it from `.vercelignore` first so it is
   uploaded).

## Local preview

```bash
npx serve .
# or
python -m http.server 8000
```

Then open <http://localhost:3000> (serve) or <http://localhost:8000> (python).
