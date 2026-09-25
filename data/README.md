# Project data

This directory separates versioned metadata and curated evidence from downloaded analytical inputs.

- [`manifests/input-manifest.json`](manifests/input-manifest.json) defines the planned input roles and acquisition candidates.
- [`manifests/resolved-manifest.json`](manifests/resolved-manifest.json) records the selected RNA route, local paths, byte sizes, and SHA-256 checksums.
- [`curated/candidate-evidence.json`](curated/candidate-evidence.json) contains the curated T0/T1 evidence rows used by the MVP.
- `inputs/` contains downloaded analytical objects and is excluded from Git because it includes large and reproducible source files.

Immutable reports, web-page snapshots, and data dictionaries live under [`../references/`](../references/); generated analysis artifacts belong under [`../results/`](../results/).

Exactly one RNA route is localized: `analyzed_h5ad`. It was selected because R is available locally but Seurat is not installed, matching the manifest's route-selection rule.
