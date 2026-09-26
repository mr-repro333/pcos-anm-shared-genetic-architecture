# Public edition note

This archive is the public edition of the analysis package that accompanies the manuscript
*Polycystic ovary syndrome and age at natural menopause: effects not yet separable*, prepared
for the repository cited in the manuscript's data availability statement.

It is derived from the master audit package:

| field | value |
|---|---|
| master archive | `FINAL_AUDIT_PACKAGE.zip` |
| bytes | 14,133,144 |
| entries | 1,356 |
| SHA-256 | `537fa88574fc811d36ad7133535794808d34df4d2306bfd0ded822163932b762` |

The journal practises double-anonymous peer review, so author-identifying content cannot sit
in a publicly readable repository while the manuscript is under review. A full-text scan of
the master archive located such content in exactly 3 files; they were withheld. A further
2 files carried a local working-directory string naming the author's computer account; that
string was replaced. Nothing else was altered, and no file in the analysis chain was
modified in any way.

## Files withheld

| path | bytes | SHA-256 | reason |
|---|---:|---|---|
| `01_MANUSCRIPT/V3_1_manuscript.docx` | 67,628 | `44ebfbc7c7749de4bf5d4c0df10a71fa2a2094bf053db284f6910d7b4f83f924` | earlier draft carrying the full author list and affiliations |
| `01_MANUSCRIPT/V3_1_manuscript.md` | 74,843 | `6405ada455a3dc2133880e32958acdc1c3d7c9335be0be3ed461c77b21cf2ba5` | earlier draft carrying the full author list and affiliations |
| `04_CODE/v31_manuscript_template.md` | 57,726 | `05b63aa2fb282bf918542dda345169f1f19b8b29739cebcc457a18b040948f6a` | manuscript template carrying the author-contributions stanza |

The hashes are recorded here so that the withholding is verifiable rather than invisible:
the master archive can be checked against them. That archive is supplied to the editorial
office with the submission and is available from the corresponding author.

## Files edited

`04_CODE/v32_package.py`

| SHA-256 before | SHA-256 after |
|---|---|
| `51b7210b055cb8049f8a4220a690de967748bfb63f5f5505481d253750d0c514` | `bdcda43ceb8da89671ce702f94b40efb71c145069e19a40277a69b371df89bd9` |

- replaced a raw-string literal naming a local working directory under the computer account with `r"<working-copy>\_pcos_v31_audit"`

`08_QC/V3_1_CLEAN_ENV_SMOKE_TEST.md`

| SHA-256 before | SHA-256 after |
|---|---|
| `9cf5a3b9085d86e7f8b7ae35afa6709be902ef7ea2a8ea5e6aff17fee86fb0a9` | `44d46925321920f3752a45c1aa92b2d853f493162bd528a8681957098ffb4588` |

- replaced a literal path naming a local temporary directory under the computer account with `<temp-dir>\v31_smoke_udiu9zni\DATA_ROOT`

The original text is deliberately not reproduced here, because doing so would restore the
local account identifier this edition removes. Its exact byte content is attested by the
SHA-256 recorded above and is present, unchanged, in the master archive.

Both are tooling files. Neither is part of the analysis chain that produces any number in
the manuscript: the first assembles the archive, the second records a smoke test.

## What is byte-identical to the master archive

| folder | files here | status |
|---|---:|---|
| `00_README/` | 9 | byte-identical to the master archive |
| `02_ANALYSIS_PLAN/` | 3 | byte-identical to the master archive |
| `03_RESULTS/` | 35 | byte-identical to the master archive |
| `04_CODE/` | 29 | edited: 04_CODE/v32_package.py |
| `05_FIGURES/` | 18 | byte-identical to the master archive |
| `06_SUPPLEMENT/` | 6 | byte-identical to the master archive |
| `07_LOGS/` | 11 | byte-identical to the master archive |
| `07_PROVENANCE/` | 10 | byte-identical to the master archive |
| `08_QC/` | 7 | edited: 08_QC/V3_1_CLEAN_ENV_SMOKE_TEST.md |
| `09_REVIEWER_SIMULATION/` | 3 | byte-identical to the master archive |
| `10_INPUTS/` | 1220 | byte-identical to the master archive |

Because every file except the five named above is byte-identical, the manifest shipped here
reproduces, entry for entry, the hashes of the corresponding entries in the master archive.
Comparing the two manifests is sufficient to confirm that statement.

## The manifest shipped here

`SHA256SUMS.txt` and `MANIFEST.tsv` are identical files listing 1352 entries as `path`,
`bytes`, `sha256`. Neither lists itself, and both were regenerated after the edits above,
which is why their own hashes differ from the master archive's.

## References to the withheld folder

`00_README/REQUIRED_DELIVERABLES.*`, the archive-assembly scripts in `04_CODE/` and the
internal consistency audit in `08_QC/` refer to `01_MANUSCRIPT/`. Those references describe
the master archive and are left exactly as written; the folder is absent here by design.

## Reproducing the analysis

Unpack the archive, restore the working data root from the manifest, and run the modules in
the order given in `00_README/README_FIRST.md`. The exposure and outcome summary statistics
are not redistributed; they are public and are identified by accession, recorded sample size,
build and URL in Supplementary Methods S9 of the manuscript.

