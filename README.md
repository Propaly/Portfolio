# Yuliyan Nikolaev — Portfolio

A single-page static portfolio (People Lead, SAP Commerce Cloud Operations).
No build step, no framework — plain HTML/CSS/JS, hosted on **GitHub Pages**.

## Structure

```
.
├── index.html      # the site (all CSS + JS + hero portrait inlined)
├── favicon.svg     # monogram favicon
├── robots.txt
├── .nojekyll       # tells GitHub Pages to skip Jekyll processing
├── assets/
│   └── yuliyan-nikolaev-portrait.jpg   # social-preview (og/twitter) image
└── README.md
```

There is **no build step**: GitHub Pages serves these files as-is, so what you
see in this folder is exactly what gets published.

## Publish to GitHub Pages

### 1. Push the repo to GitHub

From this folder:

```bash
git add -A
git commit -m "Switch portfolio to GitHub Pages"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

(If the remote already exists, use `git remote set-url origin <url>` instead of
`git remote add`.)

### 2. Turn on GitHub Pages

1. Open the repo on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set **Branch** to `main` and the folder to **`/ (root)`**, then **Save**.

Give it a minute. The site goes live at one of:

- `https://<username>.github.io/<repo>/` — for a normal repo (project page)
- `https://<username>.github.io/` — if the repo is named `<username>.github.io`

All paths in `index.html` are relative, so both URL shapes work.

### 3. (Optional) Rich link previews

After the URL is known, open `index.html` and replace the `og:image` /
`twitter:image` values with the full absolute URL, e.g.

```
https://<username>.github.io/<repo>/assets/yuliyan-nikolaev-portrait.jpg
```

and uncomment the `canonical` / `og:url` lines with your real URL. Commit and
push — Pages redeploys automatically.

## Updating the site

Edit `index.html`, then:

```bash
git add -A
git commit -m "Update portfolio"
git push
```

GitHub Pages rebuilds automatically on every push to `main`.

## Local preview

```bash
npx serve .
# or
python -m http.server 8000
```

Then open <http://localhost:3000> (serve) or <http://localhost:8000> (python).
