<div align="center">

# Cycling Data Lab

**A research program on structural lower bounds for graph-supervised learning, instantiated empirically on urban mobility, bike-share demand and materials informatics, and shipped as open, reproducible software and datasets.**

[![Affiliation](https://img.shields.io/badge/affiliation-CESI%20LINEACT-red)](https://lineact.cesi.fr)
[![License](https://img.shields.io/badge/code-MIT-yellow)](https://opensource.org/license/MIT)
[![PyPI](https://img.shields.io/pypi/v/gbfs-toolkit?label=gbfs-toolkit&color=blue)](https://pypi.org/project/gbfs-toolkit/)

</div>

We develop a **universal spectral lower bound** on the generalisation error of any
graph-supervised learner, depending only on the graph Laplacian, the target signal and the
learner's reachable feature subspace, and instantiate it across bike-share, mobility and
materials data. Drafts mature privately and are **opened as preprints and public
repositories as they go out**; alongside the theory we maintain open, research-grade
software and datasets. The repositories below are the ones currently public.

## Open repositories

| Repository | What it is |
|:--|:--|
| **[gbfs-toolkit](https://github.com/cycling-data-lab/gbfs-toolkit)** | The research-grade Python **library** for GBFS bike-share feeds: ingestion into a stable, version-independent data model, the semantic **A1-A7** static and **D1-D3** dynamic quality audit, and descriptive spatial and temporal analytics. Installable from PyPI (`pip install gbfs-toolkit`), with [versioned documentation](https://cycling-data-lab.github.io/gbfs-toolkit/) and a Zenodo DOI. |
| **[gbfs-audit-catalogue](https://github.com/cycling-data-lab/gbfs-audit-catalogue)** | A certified, anomaly-flagged reference **dataset** for bike-sharing station feeds (1,509 GBFS systems across 48 countries; 46-column schema), built on the gbfs-toolkit audit pipeline, with a [project page](https://cycling-data-lab.github.io/gbfs-audit-catalogue/). Dataset v1.0 released with a Zenodo DOI. |
| **[sbf-lean](https://github.com/cycling-data-lab/sbf-lean)** | **Machine-checked Lean 4 / Mathlib proof** of the universal spectral lower bound (Theorem 1) and the deterministic ERM-oracle core of Theorem 2, with zero `sorry`. |
| **[od-lean](https://github.com/cycling-data-lab/od-lean)** | **Machine-checked Lean 4 / Mathlib proof** of the GBFS origin-destination identifiability bounds (the `q⁻¹` Cramér-Rao limit, the bias-structure projection, and the collection-horizon law), with zero `sorry` and a SymPy cross-check. |

> **Formal verification.** A distinctive thread of the program is that its core theorems are
> *machine-checked*: the Lean developments above build with zero `sorry`, depending only on
> Lean's three standard axioms. A green CI run is the public certificate behind each claim.

## Reproducibility

Each public repository ships a pinned environment, an MIT `LICENSE` (data products inherit
upstream licences, see `LICENSE-DATA` in the catalogue) and a `CITATION.cff`; gbfs-toolkit
and gbfs-audit-catalogue releases are archived on Zenodo with a DOI. The software is
continuously tested across Python versions and operating systems, type-checked, and
published to PyPI through a test-gated release pipeline with build provenance attestation.

## People

- **Rohan Fossé** · CESI École d'Ingénieurs, Montpellier · [rohanfosse.fr](https://rohanfosse.fr) · [rfosse@cesi.fr](mailto:rfosse@cesi.fr) · [ORCID](https://orcid.org/0009-0002-2195-0198)
- **Gaël Pallares** · CESI LINEACT (EA 7527) · [ORCID](https://orcid.org/0009-0002-8680-604X)

Affiliated with [CESI LINEACT (EA 7527)](https://lineact.cesi.fr), Montpellier, France.

## How to cite

```bibtex
@misc{cyclingDataLab,
  author       = {Foss\'e, Rohan and Pallares, Ga\"el},
  title        = {{cycling-data-lab}: a research program on structural lower bounds
                  for graph-supervised learning},
  year         = {2026},
  howpublished = {\url{https://github.com/cycling-data-lab}}
}
```

<div align="center">

*One spectral lower bound, several empirical domains, with machine-checked proofs and open, reproducible artifacts.*

</div>
