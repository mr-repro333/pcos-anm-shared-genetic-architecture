# Analysis package: polycystic ovary syndrome and age at natural menopause

This repository holds the analysis code, the derived input files and the result files behind
the manuscript *Polycystic ovary syndrome and age at natural menopause: effects not yet
separable*, which is under double-anonymous peer review at *Endocrine Connections*.

It is published so that every number in the manuscript can be re-derived by someone who has
only this repository. Because the review is double-anonymous, the repository carries no
author names, affiliations or contact details; the note records what was withheld for that
reason, with the SHA-256 hashes of the withheld files.

## What is here

| item | description |
|---|---|
| `PCOS_ANM_V3_2_ANALYSIS_PACKAGE.zip` | the complete analysis package: 1,354 entries, 13.4 MiB (14,023,703 bytes) |
| `analysis_code/` | the 29 code and tooling files, extracted so they can be read without downloading the archive; byte-identical to `04_CODE/` inside it |
| `PUBLIC_EDITION_NOTE.md` | a copy of the note inside the archive, recording exactly what this edition changes relative to the master audit package |
| `LICENSE` | MIT |

## Verifying the archive

```
sha256sum PCOS_ANM_V3_2_ANALYSIS_PACKAGE.zip
# expected:
# 4e30fb46e08dd472629d3a9515392b41cb76e235ccfb2d47186879851fe8c277
```

`SHA256SUMS.txt` and `MANIFEST.tsv` inside the archive are identical files. Between them they
list every one of the 1,352 files in the archive as `path`, byte count and SHA-256, and neither
lists itself. To check the archive end to end, unpack it and verify each line of the manifest
against the file it names.

## What is inside the archive

| folder | files | contents |
|---|---:|---|
| `00_README` | 9 | how to run the archive, the executive summary and the change logs |
| `02_ANALYSIS_PLAN` | 3 | the dated analysis plan, the dataset-per-outcome table and the decision log |
| `03_RESULTS` | 35 | the result files behind every table and figure in the manuscript |
| `04_CODE` | 29 | the analysis and tooling code |
| `05_FIGURES` | 18 | the figures and the source data behind them |
| `06_SUPPLEMENT` | 6 | the supplementary tables |
| `07_LOGS` | 11 | the run logs |
| `07_PROVENANCE` | 10 | the accession resolution audit, the data download log and the reference audit |
| `08_QC` | 7 | the internal quality-control records, including the clean-environment smoke test |
| `09_REVIEWER_SIMULATION` | 3 | an adversarial read of the results |
| `10_INPUTS` | 1220 | the harmonised input files the analysis code reads |
| `(root)` | 3 | the file-level manifest and this edition's note |

## What is not included

The exposure and outcome genome-wide association summary statistics analysed here are not
redistributed: they are public, and each is identified by accession, recorded sample size,
build and URL in Supplementary Methods S9 of the manuscript. What the archive does contain is
every file the analysis code actually reads, harmonised and ready to re-run, together with the
result files that the manuscript's tables and figures are built from.

## Reproducing the analysis

Unpack the archive. `00_README/README_FIRST.md` states the run order and the entry points.
`bootstrap_data_root.py --restore` rebuilds the working data root from the bundled input files
and the manifest, and the clean-environment reproduction test re-runs every module and compares
each output field against the shipped result files. `02_ANALYSIS_PLAN/` holds the dated
analysis plan that fixed the outcome family, the dataset per outcome and the sensitivity grids
before the corrected estimates were computed.

## Licence

The code is released under the MIT license in `LICENSE`. The derived data files are provided
for verification on the same terms. The underlying summary statistics remain subject to the
terms of the repositories they came from.

