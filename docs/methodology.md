# Methodology

## Source list

This landscape is built on the [Genes4Epilepsy curated gene list](https://bahlolab.github.io/Genes4Epilepsy/) (v2026-03), maintained by the Bahlo Lab at WEHI. Genes4Epilepsy is updated twice yearly and provides the authoritative list of monogenic epilepsy genes — currently 1,078 entries.

!!! note "Citation"
    Oliver KL, Scheffer IE, Bennett MF, Grinton BE, Bahlo M, Berkovic SF. Genes4Epilepsy: An epilepsy gene resource. *Epilepsia*. 2023;64(5):1368-1375. [doi:10.1111/epi.17547](https://onlinelibrary.wiley.com/doi/10.1111/epi.17547)

## Tiering approach

Genes are grouped into three status tiers based on the depth of organized community infrastructure visible in publicly available sources. Tiering is not a judgment of disease severity, scientific importance, or therapeutic potential.

<span class="status-badge status-established">●●● Established</span>
**Active patient foundation + research infrastructure.** A registered patient organization with public web presence, a registry or natural history study, and at least one of: multi-stakeholder coordination, named therapeutic programs, or a multi-site research consortium. The 61 Established genes were verified individually for each landscape dimension.

<span class="status-badge status-emerging">●●○ Emerging</span>
**Partial or growing infrastructure.** Either a research consortium without a foundation, or a small parent-led foundation without an academic natural history study, or a community that's organized but in early stages. The 62 Emerging genes were verified for the dimensions where evidence existed.

<span class="status-badge status-background">●○○ Background</span>
**Gene confirmed in epilepsy but no organized patient community identified.** The 955 Background genes are seeded with authoritative TSV-derived data (HGNC, Entrez, Ensembl, OMIM gene ID, inheritance, phenotype group from Genes4Epilepsy) plus deterministic reference URLs. They were not verified individually beyond the source TSV.

The Established / Emerging boundary is judgment-based. The Emerging / Background boundary is binary: a gene is Emerging if a public foundation, family network, or active research consortium was identifiable as of the verification date.

## Field definitions

The dashboard surfaces these fields per gene:

`Gene` — HGNC-approved symbol from Genes4Epilepsy

`Inheritance` — From Genes4Epilepsy. AD = autosomal dominant; AR = autosomal recessive; XL = X-linked; AD/AR = mixed

`Phenotype` — From Genes4Epilepsy. DEE = developmental and epileptic encephalopathy; NDD = neurodevelopmental disorder; GGE = genetic generalized epilepsy; MCD = malformation of cortical development; FE = focal epilepsy

`Clinical disorder` — Common clinical name(s) for the gene's associated phenotype, populated for Established/Emerging genes

`Patient foundation` — Primary patient-led organization, with URL where available. Some foundations are 501(c)(3); some are international networks; some are family-led without formal incorporation

`Registry platform(s)` — Underlying technology or host of each registry/NH study, with multiple platforms allowed per gene. See the [Glossary](glossary.md) for canonical platform names

`Simons Searchlight` — Whether the gene is on the Simons Searchlight (SFARI Base) enrolled gene list

`CoRDS` — Whether Sanford CoRDS lists the gene's typical disorder. "Implicit" indicates the gene's syndromes fall within CoRDS's umbrella but no dedicated partner-org listing exists

`Therapeutic programs` — Industry programs disclosed publicly + active academic translational programs. Excludes preclinical-only academic work unless program-level

`Resources` — Deterministic links to PubMed (gene + epilepsy search), HGNC, NCBI Gene, ClinVar, gnomAD, GeneReviews search, and Orphanet gene record. These are generated for every gene whether or not the target page exists at the destination

## Verification dates

- Tier 1 / Established and Emerging deep-dive entries verified via web search **May 6, 2026**
- Programmatic enrichment URLs are deterministic and don't have a verification date
- The Genes4Epilepsy source list itself is **v2026-03**

## What we don't include

- Specific clinical trial enrollment status — verify on [clinicaltrials.gov](https://clinicaltrials.gov)
- Pricing or coverage details for approved therapies
- Patient-level data of any kind
- Editorial commentary on individual foundations or research groups
- Speculation about which therapeutic approaches will succeed

## What can go wrong

URLs change. Foundations consolidate, rebrand, or fold. Industry programs are deprioritized without public announcements. Newly identified genes get added to Genes4Epilepsy faster than the surrounding community can develop. Some foundations operate without a public web presence and aren't visible to a curation lens like this one.

This is why the landscape is framed as a **living community resource**. If you spot something inaccurate, [tell us](about.md).

## Major systematic sources

- [Genes4Epilepsy](https://bahlolab.github.io/Genes4Epilepsy/) — gene list
- [Simons Searchlight](https://www.simonssearchlight.org/) — NDD-focused research registry
- [Sanford CoRDS](https://research.sanfordhealth.org/rare-disease-registry) — generic rare-disease registry
- [Orphanet](https://www.orpha.net/) — rare disease nomenclature and gene-disorder mappings
- [OMIM](https://www.omim.org/) — gene and phenotype IDs
- [GeneReviews](https://www.ncbi.nlm.nih.gov/books/NBK1116/) — clinical gene summaries
- [COMBINEDBrain](https://www.combinedbrain.org/) — multi-foundation biorepository consortium
- [CURE Epilepsy gene grants](https://cureepilepsy.org/)
- Individual foundation websites (verified per gene)
