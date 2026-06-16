# Living Atlas — integration guide

This bundle folds the gene reference landscape and the relationship explorer into one Living Atlas, replaces the status tiers with the research readiness maturity model, and adds a self-assessment, a role based front door, an update path, and an async testing tool. Everything is static and runs on your existing MkDocs + GitHub Pages setup with no backend.

## What goes where

Drop these into your `landscape` repo, preserving paths. Files marked NEW are additions; `mkdocs.yml` replaces yours (nav only changed, theme untouched).

```
docs/index.md                         NEW  front door (role based). Also fills the
                                           previously missing Home target in your nav.
docs/atlas.md                         NEW  wrapper page for the Atlas tool
docs/self-assessment.md               NEW  wrapper page for the self-assessment
docs/maturity-model.md                NEW  the model, in prose
docs/resources.md                     NEW  resource directory by readiness level
docs/submit.md                        NEW  submit an update (GitHub issue + email)
docs/testing/async-testing.md         NEW  wrapper for the async testing tool
docs/assets/atlas.html                NEW  the unified tool (Reference, Network, Maturity)
docs/assets/self-assessment.html      NEW  the self-assessment tool
docs/assets/user-testing.html         NEW  the async user testing tool
docs/assets/published-levels.json     NEW  peer directory the self-assessment reads
.github/ISSUE_TEMPLATE/record-update.yml    NEW
.github/ISSUE_TEMPLATE/maturity-level.yml   NEW
mkdocs.yml                            REPLACE  nav extended; theme and extensions unchanged
```

Your existing `docs/dashboard.html` and the rest of the site are untouched. The Atlas does not replace the dashboard; both coexist.

## Two things to confirm before you publish

1. **The repo constant.** Three tools and one page build GitHub submission links from `REPO = "boycelab/landscape"`. If your repo path differs, change it in `docs/assets/self-assessment.html`, `docs/assets/user-testing.html`, and the inline script in `docs/submit.md`.

2. **The draft links.** Every resource link was compiled offline and is flagged draft in the interface. Verify each before publishing:

   - Rare Epilepsy Network, COMBINEDBrain, NORD, NINDS, NIH/NCATS rare disease, HHS/FDA PFDD, Data for the Common Good, RDCA-DAP, James Lind Alliance, Global Genes, Genetic Alliance, Simons Searchlight, Sanford CoRDS.
   - Source list lives in `docs/assets/` data inside `self-assessment.html` and in `resources.md`.

   The reference lens links in the Atlas (PubMed, OMIM, HGNC, NCBI, ClinVar, gnomAD, GeneReviews, Orphanet, ClinicalTrials) are deterministic from your existing landscape data and carry over from the dashboard. Provenance for the gene set (Genes4Epilepsy v2026-03; Oliver KL et al., Epilepsia 2023) is unverified in this offline build; confirm against your dashboard's citation before relying on it.

## The honesty point, by design

Maturity stages are self-assessed by organizations. There is no maturity data for any organization in this bundle, and none is fabricated.

- In the Atlas reference card, the small level read is **indicative only**, derived from observable infrastructure you already record (foundation, registry, natural history platforms). It is labeled as such.
- The **authoritative** level comes from the self-assessment, and an organization chooses whether to publish it.
- The peer directory (`published-levels.json`) starts empty. As organizations opt in through the maturity-level issue form, review each and add it to that file. The self-assessment reads it to show peers.

## How the pieces connect

- **Front door** (`index.md`) routes four roles to the right starting point.
- **Atlas** carries three views: Reference (gene depth, two lenses), Network (the explorer capability: force layout, communities, ego focus), Maturity model (interactive framework).
- **Self-assessment** computes a stage per track, a composite (the lowest reliably reached), matched resources weighted to the tracks furthest behind, and an opt-in to publish and connect.
- **Submit an update** and **publish a level** both use GitHub issue forms, which work on static hosting. Copy and email fallbacks are included.
- **Async testing** captures role based task outcomes and a short survey, submitted the same way.

## Test locally

```
pip install -r requirements.txt
mkdocs serve
```

Your deploy uses `mkdocs build --strict`. Every nav entry in the new `mkdocs.yml` points to a file in this bundle or one already in your `docs/`, so the strict build stays green. If you remove a new page, remove its nav line too.

## Scope notes

- The Network view renders communities and ego networks rather than all 1,310 nodes at once, which keeps it fast and readable. The Sankey flow from the original explorer is not carried over; say the word and it can be added.
- 173 of the 235 union genes have network neighborhoods; the rest have full reference cards and will join the network layer as that data widens. The join key (gene symbol) already exists, so this is extension, not redesign.

## Lessons learned (added)

New files in this update:

```
docs/lessons.md                          NEW  governance wrapper + the tool
docs/assets/lessons.html                 NEW  share form + browse/aggregate view
docs/assets/lessons.json                 NEW  reviewed lessons the browse view reads
.github/ISSUE_TEMPLATE/lesson-learned.yml NEW
mkdocs.yml                               nav adds "Lessons learned: lessons.md"
docs/index.md                            front door tools row adds a Lessons link
```

The tool captures what did not work, framed as fit not fault and anchored to a maturity track and stage. Partners are described by category, not name, by default. An optional name field is off by default, carries a warning, and is reserved for plain verifiable fact. A required attestation gates submission. Everything routes through GitHub issue review before publishing; the maintainer reviews, de-identifies, then adds the entry to `docs/assets/lessons.json`, which the browse view reads to show patterns by stage and approach. Copy and email fallbacks exist for submitters without a GitHub account.

Confirm the `REPO` constant in `docs/assets/lessons.html` reads `boycelab/landscape`, same as the other tools. Have counsel review the attestation text, the named entity and right of reply language in `lessons.md`, and your own exposure for republishing submissions, before you publish.

## Reports and lists (added)

`docs/reports.md` and `docs/assets/report.html` add a filterable report builder over the 235 genes and the organizations derived from them. Filter by inheritance, phenotype, recorded infrastructure, network and reference membership, indicative level, and community; choose columns; sort; and export as CSV, copied TSV, copied Markdown, or print to PDF. The active filters are written into every export. Nav gains "Reports and lists: reports.md"; the front door tools row and researcher door link to it.

This update also corrects the indicative level calculation in the Atlas and the report so a recorded "No" for Searchlight or CoRDS no longer counts as a natural history platform. Levels are now Foundation plus Registry plus an affirmative natural history platform for level 4, Foundation plus Registry for level 3, either one for level 2, and neither for level 1.
