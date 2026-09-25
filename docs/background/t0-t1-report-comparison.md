# T0 to T1: comparison of existing molecular reports

Reviewed September 25, 2026. This compares the [T0 summary](t0-report-summary.md) with the [T1 summary](t1-report-summary.md). Only existing reports were summarized; no primary-data analysis was performed. Dates describe specimens, not report-generation dates. T1 organoid findings are excluded.

**The main reported changes are higher mutation burden, lower estimated tumor purity, and additional RNA support for alterations already present at T0. The summaries do not establish newly acquired primary drivers** (ChatGPT 2026; Osteosarc n.d.-a, n.d.-b, n.d.-d).

## Genome-wide comparison

| Feature | T0: December 16, 2022 | T1: June 6, 2024 | Reading |
|---|---|---|---|
| Tumor purity | HMF 65%; DRAGEN 63% | HMF 36%; DRAGEN 34% | Lower estimated tumor fraction in the sampled tissue |
| Ploidy / genome doubling | HMF 3.25; DRAGEN 3.11; genome doubling reported | HMF 3.25; DRAGEN 3.19; genome doubling reported | Broadly unchanged |
| Mutation burden | HMF 1.30; DRAGEN 0.80 mutations/Mb | HMF 3.70; DRAGEN 4.07 mutations/Mb | Higher in both pipelines, still low |
| HRD | DRAGEN scar score 45; CHORD 0.014, proficient | DRAGEN scar score 36; CHORD 0.076, proficient | Scar score decreases; CHORD remains proficient; no settled HRD transition |
| Microsatellite status | HMF stable; DRAGEN assessment limited to 109 sites | HMF stable; DRAGEN 1.62% unstable sites | No reported conversion to MSI-high |

Source: existing pipeline comparison and T0 summary (Osteosarc n.d.-a; ChatGPT 2026). Different specimens and assays prevent attributing the measurement changes to a specific biological cause from these summaries alone.

## Alteration-level differences

| Alteration | T0 report | T1 report | Reading |
|---|---|---|---|
| H1-2 p.A197_K201del | Driver likelihood 100%; RNA 0/270 alternate/total reads | Same deletion, likelihood 100%; RNA 46/318 | Persists, with positive mutant-RNA support at T1 |
| ALB p.Leu262Val | Listed with 79% driver likelihood | Not listed in T1 ORANGE driver-variant table | Reporting difference; insufficient to conclude the mutation disappeared |
| ZNRF3 / ROS1 | Not highlighted in T0 summary | ZNRF3 p.G578S: 29% likelihood; ROS1 p.S2223Y: 0% | Additional T1 table entries; not established newly acquired drivers |
| SPRED1 disruption | Not highlighted in T0 summary | Two deletion-associated breakends | Additional T1 reporting; acquisition time not established |
| CDK4 / MDM2 gain | Reported; CDK4 is an ORANGE near-driver amplification | Gain remains in cross-pipeline summaries; no ORANGE near-driver amplification listed | Persistence with a changed reporting category |
| CTNNB1 | ORANGE: 9.0 copies, 1,277 TPM, near-driver amplification | ORANGE expression table: 3.8 copies, 1,910 TPM | Lower reported copy number despite higher expression; T0 copy-number QC warrants caution |

T0 entries are taken from the saved summary (ChatGPT 2026). T1 entries are from ORANGE (Osteosarc n.d.-b, 2–3, 7–8); persistent CDK4/MDM2 gain is also described by the comparison report (Osteosarc n.d.-a). Absence from a selected table or summary is not evidence of biological absence.

## RNA evidence for the CDKN2B-region rearrangement

The PARD3B–CDKN2B-AS1/CDKN2B rearrangement has tumor-DNA support at both timepoints and no support in the displayed matched blood. T0's listed bulk-RNA alignments show no junction reads. T1 adds 20 ONT and 5 PacBio junction reads, while the listed short-read RNA alignments remain negative (Osteosarc n.d.-d).

This is additional RNA evidence for an existing rearrangement, not first detection of the DNA event. Because assay coverage differs, these observations do not establish that transcription began between T0 and T1. Counts across reprocessed WGS alignments must not be summed as independent molecules.

## Spatial continuity

Both timepoints show fewer T-cell–malignant-cell neighbors than expected. T1 additionally reports 64% of CD8 cells inside the tumor region, showing that regional infiltration can coexist with reduced malignant-cell adjacency. Different section sizes and sampling prevent these summaries from establishing improved immune engagement (ChatGPT 2026; Osteosarc n.d.-c).

## Qualifications carried forward

- T0 ORANGE has a high-copy-number-noise warning; T1 reports QC PASS. Reported QC status improves, but this does not establish a biological improvement (ChatGPT 2026; Osteosarc n.d.-b).
- The T0 summary flags TP53 LOH as unresolved because the detailed DRAGEN T0 CNV report does not establish it in the PASS set. The earlier conversational T1 summary repeated the overview's “truncal TP53 LOH” wording too strongly; do not carry that claim forward (ChatGPT 2026).
- Driver likelihoods remain computational annotations, not clinician-confirmed causal probabilities. These reports do not establish treatment sensitivity or a clinician-designated primary driver.
- These comparisons preserve reported measurements and limitations; they are not a new longitudinal reanalysis.

## Works Cited

ChatGPT. 2026. “T0: Existing Molecular-Report Summary.” September 25. Project working document. [t0-report-summary.md](t0-report-summary.md).

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-a. “DRAGEN vs oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/comparison/.

Osteosarc. n.d.-b. “HMF ORANGE Report v4.1.2: IPISRC044_tumor_T1_ucla.” Pipeline version 2.3. Research-use-only report, 16 pp. Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/orange/ucla_T1.orange.pdf.

Osteosarc. n.d.-c. “Osteosarcoma Xenium — Analysis & Interpretation.” Accessed September 25, 2026. https://osteosarc.com/xenium/analysis/.

Osteosarc. n.d.-d. “PARD3B :: CDKN2B-AS1/CDKN2B — Fusion Evidence.” Accessed September 25, 2026. https://osteosarc.com/fusions/pard3b--cdkn2b-as1-cdkn2b/.
