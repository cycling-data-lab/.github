# cycling-data-lab

**Open research lab on cycling data.**
Bike-sharing demand, mobility-justice diagnostics, GBFS infrastructure
audits and cycling-environment composite indicators.

We build reproducible commune-level and station-level datasets for
French and international cycling networks, and the indicators that
turn those datasets into actionable inputs for transport policy.

---

## Research focus

Cycling-environment quality, bike-sharing operations and transport
equity sit at the intersection of three open-data domains: OpenStreetMap
infrastructure, GBFS station feeds, and national social-statistics
(INSEE Filosofi, FUB Barometer, EMP modal-share survey). Each repo
here packages one publication-grade contribution to that intersection,
released as code + data + reproducible LaTeX.

The lab is anchored at [CESI LINEACT (EA 7527), Montpellier, France](https://lineact.cesi.fr)
and follows an open-by-default policy : public repos, MIT licenses,
public data wherever the source allows.

## Repositories

| Repo | Topic | Status |
|---|---|---|
| [imd-national-catalogue](https://github.com/cycling-data-lab/imd-national-catalogue) | Commune-level IMD-4 + IES cycling-environment indicator on 34,858 French communes. The substrate. | Stable |
| [bikeshare-demand-forecasting](https://github.com/cycling-data-lab/bikeshare-demand-forecasting) | IMD-augmented bike-share demand prediction (27-network benchmark + leave-station-out spatial generalisation). | Submission draft |
| [bikeshare-gsp-tools](https://github.com/cycling-data-lab/bikeshare-gsp-tools) | Graph-signal-processing foundations for cycling-network expansion (spectral bounds, D-optimal siting, learning curves). | Working draft |
| [penality-analysis](https://github.com/cycling-data-lab/penality-analysis) | Triple-penalty mobility-justice diagnostic: cycling-poverty deserts at the intersection of cycling-environment deprivation, monetary poverty and structural geographic vulnerability. | Submission draft |
| [gbfs-audit-catalogue](https://github.com/cycling-data-lab/gbfs-audit-catalogue) | Reproducible audit of 1,509 GBFS bike-share feeds across 48 countries. 46-column reference dataset on 46,307 certified stations. | Stable |

## How the repos relate

```
              gbfs-audit-catalogue
                       │
                       │  (data certification)
                       ▼
              imd-national-catalogue
              (IMD-4 on 34,858 communes)
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
 bikeshare-       bikeshare-     penality-
 demand-          gsp-tools      analysis
 forecasting      (theory)       (equity)
 (prediction +
  siting empirics)
```

- `gbfs-audit-catalogue` provides the certified station inventory.
- `imd-national-catalogue` builds the supply-side composite indicator
  from open data layered on that inventory.
- The three downstream repos take the IMD-4 as a fixed input and
  study its predictive, theoretical and equity properties respectively.

## How to cite

Each repo ships a `CITATION.cff` and a BibTeX entry in its README.
Citing the lab as a whole : `cycling-data-lab` GitHub organisation,
2025--, [https://github.com/cycling-data-lab](https://github.com/cycling-data-lab).

## Reproducibility

All experiments :
- Run in Python 3.12+ with explicit `requirements.txt` per repo.
- Pin random seeds (typically `42`).
- Use only public data sources (OSM, GBFS, INSEE Filosofi, FUB,
  Open-Elevation, Lyft Trip Logs, BIXI, TfL, Citi Bike).
- Ship the trained model parquets and intermediate JSONs to bypass
  large recomputations.
- Document RAM / wall-time budget per script.

## License

All repos under [MIT License](https://opensource.org/license/MIT).
Data products inherit the upstream provider licenses (OdbL for OSM
and GBFS, INSEE open-data licence, etc.).

## Contact

Rohan Fossé — [rfosse@cesi.fr](mailto:rfosse@cesi.fr) — [ORCID 0009-0002-2195-0198](https://orcid.org/0009-0002-2195-0198)
Gaël Pallares — [ORCID 0009-0002-8680-604X](https://orcid.org/0009-0002-8680-604X)

Issues and pull requests welcome on any of the repos above.
