# T1: existing molecular-report summary

Reviewed September 25, 2026. Specimen: UCLA Th4 recurrence biopsy, June 6, 2024; UCLA tumor–normal pair. This summarizes existing retrospective research reports only. No primary-data analysis was performed. The T1-derived organoid is a separate experimental branch and is excluded from patient-biopsy findings below.

**The reports describe a whole-genome-doubled tumor with low mutation burden, candidate alterations, and long-read RNA evidence for a CDKN2B-associated rearrangement. They do not establish a clinician-designated primary driver** (Osteosarc n.d.-c, n.d.-d).

## Overall molecular profile

| Measure | oncoanalyser / HMF | DRAGEN |
|---|---|---|
| Estimated tumor purity | 36% | 34% |
| Ploidy | 3.25; whole-genome doubling reported | 3.19 |
| Tumor mutation burden | 3.70 mutations/Mb; low | 4.07 mutations/Mb |
| Microsatellite status | Stable | 1.62% unstable sites; summarized as stable |
| Homologous-recombination deficiency | CHORD probability 0.076; proficient | Genomic-scar score 36 |

Source: existing cross-pipeline comparison (Osteosarc n.d.-b). These pipelines use the same input WGS; agreement is not independent specimen replication.

The website calls DRAGEN results HRD-positive while also giving a high-HRD threshold of 42, above T1's score of 36. Preserve the numerical outputs and CHORD classification rather than treating that prose as a settled T1 HRD diagnosis (Osteosarc n.d.-b).

## Candidate alterations

The 16-page ORANGE report lists the following (Osteosarc n.d.-c, 2–3):

| Finding | Reported annotation |
|---|---|
| H1-2 p.A197_K201del | Driver likelihood 100%; RNA alternate support 46/318 reads (14%) |
| ZNRF3 p.G578S | Driver likelihood 29%; RNA alternate support 0/26 |
| ROS1 p.S2223Y | Driver likelihood 0%; RNA alternate support 0/5 |
| SPRED1 disruption | Two deletion-associated breakends involving intron 6 and exon 7 |
| CDKN2B disruption | Intron-1 breakend |
| Driver amplifications, homozygous deletions, driver fusions | None listed in those ORANGE categories |

These likelihoods are pipeline annotations, not clinician-confirmed causal probabilities. ROS1's table inclusion does not establish a ROS1 driver. ORANGE's cover lists no somatic disruption drivers, while page 3 lists SPRED1/CDKN2B breakends under driver-gene disruptions; retain that reporting distinction (Osteosarc n.d.-c, 1–3).

The DRAGEN overview describes a 12q13–q15 gain involving CDK4, MDM2, DDIT3, and ERBB3 at approximately 6–7 copies across the four analyzed pairs. The comparison page explains that the CDK4/MDM2 gain falls below its stricter high-amplification threshold in the elevated-ploidy background. Thus a reported gain and an empty ORANGE driver-amplification category need not conflict (Osteosarc n.d.-a, n.d.-b).

**TP53 qualification:** the DRAGEN overview calls TP53 LOH truncal, but the companion T0 summary identifies a caveat in the detailed T0 report. Do not treat T0 TP53 LOH, or its persistence from T0, as established by this summary (ChatGPT 2026).

## RNA and rearrangement evidence

The dedicated PARD3B–CDKN2B-AS1/CDKN2B report describes a somatic rearrangement with these T1 observations:

- Tumor WGS: 10–14 split reads depending on alignment/pipeline.
- Displayed matched blood: no split-read support.
- Long-read RNA: 20 ONT and 5 PacBio split reads.
- Listed short-read RNA datasets: no split-read support.

These are published report counts, not newly calculated results. Counts across reprocessed WGS alignments must not be added as independent molecules. The dedicated report supports an expressed rearrangement; ORANGE's absence of a driver-fusion entry is a different reporting category (Osteosarc n.d.-f).

ORANGE lists CTNNB1, MDM2, and CDK4 among highly expressed genes, and CDKN2A/CDKN2B at 0 TPM. These are expression annotations, not independent driver determinations (Osteosarc n.d.-c, 7–8).

## Spatial and single-cell reports

The Xenium report includes one T1 section with 29,787 QC-passing cells (86%). It reports 64% of CD8 cells inside the tumor region, reduced T-cell–malignant-cell adjacency (neighborhood-enrichment z = −13.2), and enriched CD8–macrophage adjacency (z = +19.1). Regional infiltration and direct malignant-cell proximity are distinct measurements. The report cautions that this is one patient, with independently annotated samples and a targeted panel (Osteosarc n.d.-e).

The single-cell variant browser includes T1 ONT and 10x RNA genotyped at bulk-WGS somatic sites. Numerical results did not load in the retrieved page, so no T1-specific cell counts or variant distributions are summarized here (Osteosarc n.d.-g).

## QC and interpretation limits

ORANGE reports QC PASS, no germline driver variants, and no detected alterations among its listed genetic immune-escape mechanisms. These negative categories are limited to what the pipeline assessed. The PDF is explicitly research-use-only (Osteosarc n.d.-c, 1, 5–6, 12).

## Works Cited

ChatGPT. 2026. “T0: Existing Molecular-Report Summary.” September 25. Project working document. [t0-report-summary.md](t0-report-summary.md).

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-a. “DRAGEN Somatic Analysis.” Accessed September 25, 2026. https://osteosarc.com/dragen/.

Osteosarc. n.d.-b. “DRAGEN vs oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/comparison/.

Osteosarc. n.d.-c. “HMF ORANGE Report v4.1.2: IPISRC044_tumor_T1_ucla.” Pipeline version 2.3. Research-use-only report, 16 pp. Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/orange/ucla_T1.orange.pdf.

Osteosarc. n.d.-d. “oncoanalyser — Sid's Data.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/.

Osteosarc. n.d.-e. “Osteosarcoma Xenium — Analysis & Interpretation.” Accessed September 25, 2026. https://osteosarc.com/xenium/analysis/.

Osteosarc. n.d.-f. “PARD3B :: CDKN2B-AS1/CDKN2B — Fusion Evidence.” Accessed September 25, 2026. https://osteosarc.com/fusions/pard3b--cdkn2b-as1-cdkn2b/.

Osteosarc. n.d.-g. “Tumor Somatic Variants at Single-Cell Resolution.” Accessed September 25, 2026. https://osteosarc.com/scrnaseq/tumor_variants/.
