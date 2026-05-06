# Boyce Lab Genetic Epilepsy Landscape — Site

[MkDocs](https://www.mkdocs.org/) source for the Boyce Lab Genetic Epilepsy Landscape, using the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

---

## 🚀 Deploying to GitHub Pages

The repo includes `.github/workflows/deploy.yml`, which builds the site and deploys it automatically on every push to `main`. **You need to enable Pages with the right source — once.**

### One-time setup

1. **Push this repo to GitHub** (on the `main` branch, including the `.github/` folder)..
2. Go to your repo → **Settings** → **Pages**.
3. Under **Source**, select **GitHub Actions** (not "Deploy from a branch").
4. Push any commit, or trigger the workflow manually under **Actions** → **Deploy MkDocs site** → **Run workflow**.

That's it. After the workflow completes (~1–2 min), the site is live at `https://<your-user>.github.io/<repo-name>/`.

### Why this matters

If you set Pages to **"Deploy from a branch"** with the source as `main` / root, GitHub Pages will just render the README.md of the repo root — which is what you're probably seeing right now. We need Pages to serve the **built** site (the `site/` folder MkDocs produces), not the source markdown.

The Actions workflow handles this: it runs `mkdocs build`, uploads the result as a Pages artifact, and deploys it. No `gh-pages` branch, no force pushes, no manual steps after setup.

### Updating site_url

`mkdocs.yml` is set to `https://boycelab.github.io/landscape/`. If your repo name or username is different, update `site_url:` to match — otherwise sitemap and canonical URLs will point to the wrong place.

---

## Alternative: manual one-shot deploy

If you don't want GitHub Actions, you can run the build locally and push to a `gh-pages` branch yourself:

```bash
pip install -r requirements.txt
mkdocs gh-deploy --force
```

Then in **Settings** → **Pages**, set the source to **Deploy from a branch** → `gh-pages` / `(root)`.

You'll need to re-run `mkdocs gh-deploy` every time you want to publish updates.

---

## Local development

```bash
# Set up a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Start dev server (auto-reloads on changes)
mkdocs serve
```

Visit <http://127.0.0.1:8000>. Edits to markdown files reload automatically.

```bash
# Just build, no serve
mkdocs build
```

Output goes to `site/` (gitignored — don't commit it).

---

## What's here

```
.
├── .github/workflows/deploy.yml    # auto-deploy to GitHub Pages
├── mkdocs.yml                      # site configuration
├── requirements.txt                # Python dependencies
├── README.md                       # this file
└── docs/
    ├── index.md                    # landing page
    ├── dashboard.md                # embeds the interactive dashboard
    ├── methodology.md              # how the landscape was built
    ├── glossary.md                 # platforms, abbreviations, conventions
    ├── data.md                     # spreadsheet download + citation
    ├── about.md                    # Boyce Lab info + contact
    ├── stylesheets/
    │   └── extra.css               # purple palette + dashboard iframe styling
    └── assets/
        ├── dashboard.html          # standalone interactive dashboard
        └── BoyceLab_Genetic_Epilepsy_Landscape.xlsx
```

---

## Updating content

**Site copy (markdown pages)** — Edit files in `docs/` directly. Push to main; the workflow rebuilds and redeploys.

**Dashboard** — The dashboard is the standalone HTML file at `docs/assets/dashboard.html`. To regenerate after data changes:

1. Edit the source data files (in the broader `landscape/` build directory)
2. Run `python build_html.py`
3. Copy the regenerated `BoyceLab_Genetic_Epilepsy_Landscape.html` to `docs/assets/dashboard.html`
4. Commit and push

**Spreadsheet** — Same flow with `python build_xlsx.py`, copy to `docs/assets/`.

---

## Customization notes

- **Colors** — Defined in `docs/stylesheets/extra.css` via Material CSS variables (`--md-primary-fg-color` etc.). Palette matches the dashboard's purple (`#6d28d9`).
- **Fonts** — Set in `mkdocs.yml` under `theme.font` — Public Sans for body, JetBrains Mono for code, plus Fraunces loaded for headings via the custom CSS.
- **Navigation** — Edit the `nav:` block in `mkdocs.yml`.
- **Search** — Built into Material; works automatically across all markdown content. The dashboard's own search is separate (it indexes the gene data).

---

## Other hosts (Netlify, Cloudflare, anywhere static)

The Actions workflow targets GitHub Pages, but `mkdocs build` produces a vanilla static `site/` folder you can host anywhere.

**Netlify** — Connect repo, build command `mkdocs build`, publish directory `site`, add `mkdocs-material` via `requirements.txt` with `PYTHON_VERSION=3.12` env var.

**Cloudflare Pages** — Same as Netlify; auto-detects Python.

**Static hosts (S3, Vercel, nginx, etc.)** — Run `mkdocs build` locally, upload the `site/` folder.

---

## License and reuse

See [`docs/data.md`](docs/data.md) for citation guidance and reuse expectations.
