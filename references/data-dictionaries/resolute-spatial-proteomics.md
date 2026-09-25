# Resolute Bio — Spatial Proteomics

Contributed by [Resolute Bio](https://www.resolute.bio).

## Contents


| File                      | Size   | Description                                     |
| ------------------------- | ------ | ----------------------------------------------- |
| `T0_B1_he_image.ome.tiff` | 414 MB | H&E whole-slide image, pyramidal OME-TIFF       |
| `T0_B1_metadata.tsv`      | 37 KB  | One row per measured region: location and yield |
| `T0_B1_pg_matrix.tsv`     | 9.8 MB | Protein group quantities, 7,979 × 247           |
| `T0_B1_pr_matrix.tsv`     | 59 MB  | Precursor quantities, 68,313 × 247              |


At a glance:

- 304 regions of one section, each 112 × 112 µm, were selected for laser capture microdissection, chosen to span the section's morphological diversity
- 247 of those regions were measured by DIA mass spectrometry; these files describe those 247
- 232 of the measured regions passed quality control; the rest are included but flagged
- Median 4,674 protein groups and 25,421 precursors per passing region (3,178–5,898 protein groups)
- Whole-slide image 60,663 × 63,139 px at 0.274 µm/px, brightfield 20×



## `T0_B1_metadata.tsv`


| Column                  | Description                                                                          |
| ----------------------- | ------------------------------------------------------------------------------------ |
| `sample_id`             | Region identifier. Joins to the matrix column headers                                |
| `segmented_tissue_id`   | Segmented tissue region this sample came from. IDs are stable labels, not contiguous |
| `geometry`              | Region outline as WKT, in pixel coordinates of `T0_B1_he_image.ome.tiff` (level 0)   |
| `proteins_identified`   | Protein groups identified in this region                                             |
| `precursors_identified` | Precursors identified in this region                                                 |
| `filter_stage`          | Quality control outcome — see below                                                  |


`filter_stage` values:


| Value                | Regions | Meaning                                    |
| -------------------- | ------- | ------------------------------------------ |
| `analyzed`           | 232     | Passed quality control                     |
| `excluded_low_depth` | 15      | Too few precursors to keep in the analysis |


Excluded regions are kept in all three files so the full measured layout stays visible. Filter on `filter_stage == "analyzed"` to reproduce the analysis set.

## `T0_B1_pg_matrix.tsv` and `T0_B1_pr_matrix.tsv`

Protein-group-level and precursor-level quantities, one row per feature and one column per region. Both files share leading identifier columns; every remaining column is a `sample_id`. Rows are the features quantified in at least one of the 247 regions.

`T0_B1_pg_matrix.tsv` — 7,979 rows:

`Protein.Group`, `Protein.Ids`, `Protein.Names`, `Genes`

`T0_B1_pr_matrix.tsv` — 68,313 rows:

`Protein.Group`, `Protein.Ids`, `Protein.Names`, `Genes`, `Proteotypic`, `Stripped.Sequence`, `Modified.Sequence`, `Precursor.Charge`

## Contact

Questions about this dataset: [resolute.bio](https://www.resolute.bio)