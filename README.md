# Fusion Partner Context

This repository is preparing a reproducible tool that reports existing rearrangement evidence, T1 single-cell RNA expression, and T0 spatial-protein abundance for one selected gene pair.

## Repository map

- [`docs/project-plan.md`](docs/project-plan.md) defines the scientific and implementation contract.
- [`docs/background/`](docs/background/) contains authored summaries of the existing T0 and T1 reports.
- [`references/`](references/) contains immutable third-party reports, web snapshots, and data dictionaries retained for provenance.
- [`data/manifests/`](data/manifests/) contains the planned and resolved input manifests.
- [`data/curated/`](data/curated/) contains small, versioned evidence inputs.
- `data/inputs/` contains downloaded analytical inputs and is intentionally excluded from Git.
- `results/` is reserved for generated reports, tables, plots, and preflight artifacts.

Large inputs and generated results are not source-controlled. Their source URLs, sizes, and SHA-256 checksums are recorded in [`data/manifests/resolved-manifest.json`](data/manifests/resolved-manifest.json).

## Local setup

The project uses Python 3.11 and [uv](https://docs.astral.sh/uv/) for a reproducible environment:

```bash
uv sync
uv run pytest
```

The required ClawBio skill is vendored locally at [`.agents/skills/celltype-specificity-profiler/`](.agents/skills/celltype-specificity-profiler/). Its immutable upstream source and file checksums are recorded in [`.agents/skills.lock.json`](.agents/skills.lock.json). The profiler is intentionally limited to cell-type expression summaries; the project plan remains authoritative for clustering, differential expression, spatial-protein analysis, and reporting.
