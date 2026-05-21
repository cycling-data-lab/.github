<div align="center">

# cycling-data-lab

**Reproducible research on cycling-environment quality, bike-share demand and mobility justice.**

[![Repos](https://img.shields.io/badge/repositories-5-blue)](https://github.com/orgs/cycling-data-lab/repositories)
[![License](https://img.shields.io/badge/license-MIT-yellow)](https://opensource.org/license/MIT)
[![Data](https://img.shields.io/badge/data-open-success)](#open-data-and-reproducibility)
[![Affiliation](https://img.shields.io/badge/affiliation-CESI%20LINEACT-red)](https://lineact.cesi.fr)

</div>

---

## What we work on

We measure **cycling environments**, **bike-share demand** and the
**social distribution** of both, at the granularity at which French
transport policy is actually decided — the commune (n = 34,858) and
the station (n ≈ 50,000 across France + 6 international networks).

Three open-data substrates — OpenStreetMap infrastructure, GBFS
station feeds, INSEE social-statistics — meet here in a single
research pipeline that produces:

- a **commune-level supply-side composite indicator** (the IMD-4) that
  beats the de facto French standard (Cerema cycling-infrastructure
  density) by +18 pts R² in predicting realised commuting share;
- a **demand-prediction benchmark** on 27 dock-based networks across
  two continents, with paired bootstrap CIs and an explicit
  decomposition of the +0.27 headline ΔR² into transferable-spatial
  and station-fingerprint components;
- a **mobility-justice diagnostic** that turns the indicator into a
  ranked, intersectional priority list of 322 cycling-poverty deserts
  for the 2023–2027 Plan Vélo;
- a **graph-signal-processing toolkit** that develops the spectral
  bounds, sampling-theoretic siting and empirical learning curves
  that underpin the prediction work.

All released as code + data + reproducible LaTeX under MIT.

---

## Repository map

```
                   ┌──────────────────────────┐
                   │   gbfs-audit-catalogue   │   1,509-feed audit, 46,307 stations
                   │     (data certification) │   48 countries
                   └────────────┬─────────────┘
                                │
                                ▼
                   ┌──────────────────────────┐
                   │ imd-national-catalogue   │   IMD-4 + IES on
                   │     (substrate, n=34,858)│   34,858 French communes
                   └────────────┬─────────────┘
                                │
              ┌─────────────────┼─────────────────┐
              ▼                 ▼                 ▼
   ┌──────────────────┐ ┌────────────────┐ ┌──────────────────┐
   │ bikeshare-demand-│ │  bikeshare-    │ │   penality-      │
   │   forecasting    │ │   gsp-tools    │ │    analysis      │
   │  (prediction +   │ │   (theory)     │ │   (equity)       │
   │   LSO siting)    │ │                │ │                  │
   └──────────────────┘ └────────────────┘ └──────────────────┘
```

| Repository | Contribution | Method | Status |
|---|---|---|---|
| **[imd-national-catalogue](https://github.com/cycling-data-lab/imd-national-catalogue)** | IMD-4 cycling-environment composite on 34,858 French communes | Bayesian simplex MCMC calibrated on FUB + EMP panels | v0.2 beta · v1.0 Hugging Face + Zenodo coming |
| **[bikeshare-demand-forecasting](https://github.com/cycling-data-lab/bikeshare-demand-forecasting)** | IMD-augmented bike-share demand prediction (temporal + leave-station-out) | LightGBM + paired station bootstrap (B = 1000) on 9-network LSO panel | Submission draft (Transport Policy / JTG / TR-D) |
| **[bikeshare-gsp-tools](https://github.com/cycling-data-lab/bikeshare-gsp-tools)** | Graph-signal-processing foundations for cycling-network expansion | Symmetric Laplacian spectral bounds + D-optimal greedy submodular siting (Nemhauser 1-1/e) | Working draft, needs deeper theory before submission |
| **[penality-analysis](https://github.com/cycling-data-lab/penality-analysis)** | Triple-penalty mobility-justice diagnostic | Deterministic intersection of three vulnerability layers on the IMD-4 substrate | Submission draft |
| **[gbfs-audit-catalogue](https://github.com/cycling-data-lab/gbfs-audit-catalogue)** | Reproducible audit of 1,509 GBFS bike-share feeds across 48 countries | 46-column reference schema with anomaly-detection layer | Stable, Zenodo-archived |

---

## Open data and reproducibility

Every result in every repo can be reproduced from the raw open-data
sources :

- **OpenStreetMap** (OdbL) — cycling infrastructure (I axis), heavy-
  transit stops (M axis proxy).
- **GBFS** feeds (provider terms) — station inventory + real-time
  status for the 27-network panel.
- **INSEE Filosofi** (Licence Ouverte 2.0) — commune-level median
  income, poverty rate, part-vélo-travail outcome.
- **Open-Elevation** SRTM 30 m (CC-BY) — topography (T axis).
- **FUB Baromètre Vélo**, **EMP** survey, **Cerema** cycling-
  infrastructure inventory — calibration / comparison panels.
- **Lyft / Bluebikes / BIXI / TfL / Citi Bike** trip logs — 37 M
  observations across the Tier 1 panel.

Each repo ships:

- a `requirements.txt` pinning the Python stack,
- random seeds (typically `42`) and explicit RAM / wall-time
  budgets per script,
- pre-computed intermediate parquets to bypass long recomputations,
- a `CITATION.cff` for machine-readable citation,
- an MIT `LICENSE` for the code (data products inherit upstream
  licenses).

---

## How to cite

```bibtex
@misc{cyclingDataLab,
  author       = {Foss\'e, Rohan and Pallares, Ga\"el},
  title        = {{cycling-data-lab}: open research on cycling
                  environments, bike-share demand and mobility justice},
  year         = {2025--2026},
  howpublished = {\url{https://github.com/cycling-data-lab}}
}
```

Per-repo BibTeX entries are in the corresponding `README.md`.

---

## People

**Rohan Fossé** — PhD candidate, CESI École d'Ingénieurs, Montpellier
[![email](https://img.shields.io/badge/email-rfosse%40cesi.fr-blue?logo=protonmail&logoColor=white)](mailto:rfosse@cesi.fr)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--2195--0198-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-2195-0198)

**Gaël Pallares** — Research supervisor, CESI LINEACT (EA 7527)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--8680--604X-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-8680-604X)

Affiliated with [CESI LINEACT (EA 7527)](https://lineact.cesi.fr),
Montpellier, France.

---

## Contributing

Issues and pull requests welcome on any of the repos. We follow a
publish-then-discuss model: pre-prints are released as drafts
(`bikeshare-gsp-tools` is currently in this state) and feedback
shapes the final submission.

For larger collaborations (joint papers, data sharing, code
contributions), email Rohan directly.

---

<div align="center">

*Cycling data, open by default.*

</div>
