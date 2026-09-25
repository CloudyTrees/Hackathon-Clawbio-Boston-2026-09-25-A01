# Source references retained for the fusion-context MVP

Downloaded September 25, 2026. This directory contains the smallest useful set of existing reports and report-like source snapshots needed to support the proposed one-pair MVP. It intentionally excludes raw sequencing, large processed expression objects, and the protein abundance matrices; those are analysis inputs rather than existing reports.

| Local file | Role in the plan | Source | SHA-256 |
| --- | --- | --- | --- |
| [`molecular-reports/T0_personalis_ORANGE_v4.1.2.pdf`](molecular-reports/T0_personalis_ORANGE_v4.1.2.pdf) | T0 molecular context and candidate evidence; 17 pages | https://osteosarc.com/oncoanalyser/orange/personalis.orange.pdf | `dff5162c0b7cee51fbe3495e1b01b9a6eedd6bbb1f60489fa23b180454956331` |
| [`molecular-reports/T1_ucla_ORANGE_v4.1.2.pdf`](molecular-reports/T1_ucla_ORANGE_v4.1.2.pdf) | T1 molecular context and candidate evidence; 16 pages | https://osteosarc.com/oncoanalyser/orange/ucla_T1.orange.pdf | `ec0151ece2923872eec7fd086d0f8b095560ac0630a0a35bc446067ea9118717` |
| [`web-snapshots/pard3b-cdkn2b-fusion-evidence.html`](web-snapshots/pard3b-cdkn2b-fusion-evidence.html) | Primary evidence snapshot for the provisional rearrangement candidate, including assay/library-level T0/T1 support | https://osteosarc.com/fusions/pard3b--cdkn2b-as1-cdkn2b/ | `9944397e3ed1781eaa32636b6146ef69c8296c2ac27db10167f23abc317cbbf5` |
| [`web-snapshots/dragen-oncoanalyser-comparison.html`](web-snapshots/dragen-oncoanalyser-comparison.html) | Cross-pipeline purity, ploidy, TMB, MSI, and HRD context used by the T0/T1 summaries | https://osteosarc.com/oncoanalyser/comparison/ | `1df297a0be788bb4402b3e8f420ea2bcd80c83fcf1a84fc2faa486601989a4af` |
| [`web-snapshots/xenium-analysis.html`](web-snapshots/xenium-analysis.html) | Spatial RNA context and limitations for T0/T1; retained as supporting context, not as a substitute for the planned T1 scRNA and T0 protein analyses | https://osteosarc.com/xenium/analysis/ | `ab6b56d6d1289c9d8018a23c141f7bb7349f0d23842d4e49543790c368c886f8` |
| [`data-dictionaries/resolute-spatial-proteomics.md`](data-dictionaries/resolute-spatial-proteomics.md) | Data dictionary for the required T0 spatial-proteomics matrix and region metadata | https://sid-sijbrandij-osteosarc-dataset.s3.us-west-2.amazonaws.com/vendor/resolute.bio/README.md | `61526a655cd11e52fc88929b7fe21147708dc500ff44a61f19ef01747e4de038` |

The HTML files are source-page snapshots. Their linked images, scripts, and other remote assets may still require network access when opened. The ORANGE PDFs are self-contained.

The DRAGEN detail pages, oncoanalyser subpages, data catalog, pathology catalog, and single-cell variant browser were not duplicated here because the saved reports above cover the MVP's immediate evidence and interpretation needs. They remain cited in the project summaries and can be revisited if the candidate or analysis scope changes.
