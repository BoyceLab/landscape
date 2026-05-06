# Boyce Lab Genetic Epilepsy Landscape — Site

This is the [MkDocs](https://www.mkdocs.org/) source for the Boyce Lab Genetic Epilepsy Landscape site, using the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

## Contents

```
.
├── mkdocs.yml                  # site configuration
├── requirements.txt            # Python dependencies
├── README.md                   # this file
└── docs/
    ├── index.md                # landing page
    ├── dashboard.md            # embeds the interactive dashboard
    ├── methodology.md          # how the landscape was built
    ├── glossary.md             # platforms, abbreviations, conventions
    ├── data.md                 # spreadsheet download + citation
    ├── about.md                # Boyce Lab info + contact
    ├── stylesheets/
    │   └── extra.css           # purple palette + dashboard iframe styling
    └── assets/
        ├── dashboard.html      # standalone interactive dashboard
        └── BoyceLab_Genetic_Epilepsy_Landscape.xlsx
```

## Local development

You'll need Python 3.9 or newer.

```bash
# Set up a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate   # on Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Start the dev server (auto-reloads on changes)
mkdocs serve
```

The site will be at <http://127.0.0.1:8000>. Edits to markdown files reload automatically.

## Building the static site

```bash
mkdocs build
```

This produces a fully static site in `site/` that you can serve from any web host.

## Deploying

### Option A — GitHub Pages (easiest)

1. Push this repo to GitHub
2. Run `mkdocs gh-deploy` — this builds the site and pushes to a `gh-pages` branch
3. Enable GitHub Pages on the `gh-pages` branch in repo Settings → Pages

Set the URL in `mkdocs.yml` (`site_url:`) to your GitHub Pages URL before deploying.

### Option B — Netlify

1. Push this repo to GitHub
2. In Netlify: New site from Git → connect the repo
3. Build command: `mkdocs build`
4. Publish directory: `site`
5. Add `mkdocs-material` to a Python build (set `PYTHON_VERSION` env var to `3.11` and add a `runtime.txt` containing `3.11`)

### Option C — Cloudflare Pages

Similar to Netlify. Build command `mkdocs build`, output directory `site`. Cloudflare will detect Python automatically.

### Option D — Any static host

`mkdocs build` produces a vanilla static `site/` folder. Upload it to S3 + CloudFront, Vercel, Render, your own nginx server, anywhere that serves static HTML.

## Updating content

### Updating the dashboard

The dashboard is the standalone HTML file at `docs/assets/dashboard.html`. To regenerate after edits:

1. Edit the source data files (see the `landscape/` build directory in the broader project)
2. Run `python build_html.py` to regenerate `BoyceLab_Genetic_Epilepsy_Landscape.html`
3. Copy the regenerated file to `docs/assets/dashboard.html` here
4. Run `mkdocs build` (or just `mkdocs serve` to preview)

### Updating the spreadsheet

Same flow — regenerate via `python build_xlsx.py` and copy to `docs/assets/`.

### Updating site copy

Edit the markdown files in `docs/` directly. The Material theme handles the rest.

## Customization notes

- **Colors:** Defined in `docs/stylesheets/extra.css` via Material CSS variables (`--md-primary-fg-color` etc). The palette matches the dashboard's purple (`#6d28d9`).
- **Fonts:** Set in `mkdocs.yml` under `theme.font` — Public Sans for body, JetBrains Mono for code, plus Fraunces loaded for headings via the custom CSS.
- **Navigation:** Edit the `nav:` block in `mkdocs.yml`.
- **Search:** Built into Material; works automatically across all markdown content. The dashboard's own search is separate (it indexes the gene data).

## License and reuse

See the main [data downloads page](docs/data.md) for citation guidance and reuse expectations.
