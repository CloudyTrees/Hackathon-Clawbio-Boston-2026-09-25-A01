# T0 versus T1: data availability comparison

Reviewed September 25, 2026.

This document summarizes the existing public data catalog and reports. No primary sequencing data were reanalyzed. T0 and T1 refer to specimen collection dates, not dates when the retrospective analyses were performed.

**T0 has broader documented profiling of the original resection; T1 adds tumor single-cell sequencing, long-read RNA, and a patient-derived organoid. Both have tumor–normal DNA sequencing, bulk RNA, and spatial data.**

## Available datasets

| Dimension | T0 — December 16, 2022 | T1 — June 6, 2024 |
|---|---|---|
| Specimen | Primary spinal tumor resection, UCSF | Recurrent tumor biopsy, UCLA |
| Short-read WGS | Tumor and matched normal; Personalis and Natera datasets listed | UCLA tumor and blood normal, plus organoid WGS |
| WES | Multiple providers: BostonGene, CeGaT, Natera | BostonGene and Tempus |
| Bulk RNA-seq | Available, including multiple providers | Available |
| Tumor scRNA-seq | Not listed in the tumor single-cell catalog | 10x gene expression, TCR and BCR; processed cell annotations and analysis objects |
| Long-read RNA | Not listed | Both ONT and PacBio, including single-cell long-read data |
| Xenium spatial RNA | Two tissue blocks, B3 and C3 | One section, 0102917 |
| Organoid model | No T0-derived organoid listed | T1-derived organoid, analyzed separately from the biopsy |

Source: Osteosarc (n.d.-a). “Not listed” means availability has not been established; it does not establish that the assay was never performed. The catalog flags the Natera WGS tumor/normal assignment as inferred rather than vendor-confirmed.

T0 also has substantially more documented tissue-imaging and protein profiling: numerous H&E blocks, Orion 18-plex imaging, and spatial mass-spectrometry proteomics. T1 has an H&E biopsy slide and Xenium, but equivalent T1 Orion/spatial mass-spectrometry datasets are not listed on the pathology page (Osteosarc n.d.-d).

## Report-level differences relevant to comparisons

| Report property | T0 | T1 |
|---|---|---|
| ORANGE-estimated tumor purity | 65% | 36% |
| Overall QC shown on report cover | High copy-number noise warning | PASS |

Sources: the T0 and T1 ORANGE reports (Osteosarc n.d.-b, n.d.-c).

These are existing pipeline estimates and flags, not recalculated measurements. The reports indicate differences in estimated tumor content and technical quality as well as collection time. ORANGE reports are labeled Research Use Only; these entries do not establish a clinician-designated driver interpretation.

## Comparisons supported by the listed data

- **DNA and bulk RNA:** available at both timepoints.
- **DNA, single-cell RNA, and long-read transcripts:** T1 has the necessary listed modalities.
- **Tumor and organoid:** available for T1. The organoid is a separate experimental branch, not a later patient timepoint.
- **Spatial comparisons:** possible between T0 and T1, while preserving the distinction between two resection blocks and one biopsy section.
- **Long-read genomic DNA or methylation:** neither timepoint has verified availability in the public catalog reviewed here. This is not an exhaustive audit of every file in the bucket.

Availability basis: Osteosarc (n.d.-a, n.d.-d). These statements identify potential comparisons; they do not establish that specimens, processing, or measurements are directly interchangeable.

## Works Cited

Osteosarc. n.d.-a. “Data Files.” *Sid Sijbrandij’s Osteosarcoma Data*. Accessed September 25, 2026. https://osteosarc.com/data/.

Osteosarc. n.d.-b. “ORANGE Report: IPISRC044_tumor_T0_personalis.” *Sid Sijbrandij’s Osteosarcoma Data*. Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/orange/personalis.orange.pdf.

Osteosarc. n.d.-c. “ORANGE Report: IPISRC044_tumor_T1_ucla.” *Sid Sijbrandij’s Osteosarcoma Data*. Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/orange/ucla_T1.orange.pdf.

Osteosarc. n.d.-d. “Pathology.” *Sid Sijbrandij’s Osteosarcoma Data*. Accessed September 25, 2026. https://osteosarc.com/pathology/.
