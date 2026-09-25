# T0: existing molecular-report summary

Reviewed September 25, 2026. Specimen: UCSF spinal tumor resection, December 16, 2022; Personalis tumor–normal pair. This summarizes retrospective research analyses of that specimen, not a clinical report issued in December 2022. The principal consolidated source is the 17-page ORANGE report, supplemented by the site's DRAGEN, variant, rearrangement, and spatial analyses (Osteosarc n.d.-h).

**T0 already shows extensive copy-number alteration, approximately triploid tumor DNA content, and low small-mutation burden. Several candidate alterations are reported, but these sources do not establish a clinician-designated primary driver** (Osteosarc n.d.-e, n.d.-h).

## Overall molecular profile

| Measure | oncoanalyser / HMF | DRAGEN | Reading |
|---|---|---|---|
| Estimated tumor purity | 65% | 63% | Similar estimates of tumor fraction. |
| Ploidy | 3.25 | 3.11 | Approximately triploid; HMF also calls whole-genome duplication. |
| Tumor mutation burden | 1.30 mutations/Mb | 0.80 mutations/Mb | Both low; retain pipeline-specific values. |
| Microsatellite instability | Stable | 8/109 sites unstable, 7.34% | Limited DRAGEN assessable sites weaken the T0 comparison. |
| Homologous-recombination deficiency | CHORD probability 0.014; proficient | Genomic-scar score 45 | Discordant methods, not a settled HRD classification. |

Sources: comparison, overview, and DRAGEN QC reports (Osteosarc n.d.-d, n.d.-c, n.d.-h). These pipelines analyze the same input DNA; agreement is analytical corroboration, not independent specimen replication.

## Candidate alterations

| Alteration | What is reported at T0 | Interpretation boundary |
|---|---|---|
| **H1-2 p.Ala197_Lys201del** | In-frame deletion; HMF driver score 1.000. DNA VAF 15%, depth 87. | A computational driver nomination, not clinician confirmation. |
| **ALB p.Leu262Val** | Missense variant; HMF driver score 0.791. DNA VAF 9%, depth 47. | Its score alone does not establish a causal role in this osteosarcoma. |
| **CDK4 / MDM2 region gain** | DRAGEN reports the 12q amplicon at roughly 6–7 copies. ORANGE lists CDK4 at 8.4 copies and 490.8 TPM, classified as a near-driver amplification. | The gain is reported across analyses; exact copy number and reporting category differ. |
| **CTNNB1 gain** | ORANGE lists 9.0 copies and 1,277 TPM, also classified as a near-driver amplification. | A copy-number/expression finding; this is not a reported activating CTNNB1 sequence mutation. |
| **CDKN2B-region rearrangement** | A PARD3B–CDKN2B-AS1/CDKN2B junction has T0 tumor-DNA split reads and none in the displayed matched blood. The driver catalog records CDKN2B disruption with likelihood 0.000. | Evidence supports a somatic rearrangement; the catalog does not establish biallelic CDKN2B inactivation. |
| **CDKN2A LOH** | DRAGEN reports total CN about 2 and minor-allele CN 0. | Loss of heterozygosity does not by itself demonstrate complete loss of function. |

Sources: driver and SNV catalogs, ORANGE pp. 2–3, DRAGEN CNV, and the detailed rearrangement report (Osteosarc n.d.-b, n.d.-e, n.d.-f, n.d.-j, n.d.-k). The published pages do not resolve whether the CDK4 numerical discrepancy reflects analysis versions, different summaries, or another cause.

## What RNA and spatial evidence add

**ORANGE's RNA-depth column matters:** H1-2 has **0/270 mutant/total RNA reads**, whereas ALB has **0/0**. The former is a covered site without observed mutant reads in this analysis; the latter has no informative coverage. Neither supplies positive mutant-RNA support here, and neither alone disproves the DNA call (Osteosarc n.d.-f, 2).

For the **CDKN2B-region junction**, the report lists **16–19 split reads per T0 tumor-DNA alignment**, zero in matched blood, and zero in the two displayed T0 bulk-RNA alignments. Positive long-read RNA observations belong to T1–T3. Do not add the T0 counts across reprocessed BAMs as independent molecules or transfer later RNA support to T0 (Osteosarc n.d.-j).

The Xenium analysis includes two T0 specimens, B3 and C3, with **235,950 and 348,052 QC-passing cells**. It reports tumor-enriched allele-probe signals for DYNC1H1, ZNF436, TECPR1, and EXOC4 across all six sections, including both T0 sections. It also reports fewer T-cell–malignant-cell neighbors than expected in both T0 specimens. These support spatial localization observations, not driver causality or observed immune killing. The targeted probes yield pseudo-VAFs, and cell identities are inferred from expression (Osteosarc n.d.-i).

## Qualifications that change the interpretation

- **Copy-number QC:** ORANGE carries a high-copy-number-noise warning. Its exact CN values deserve caution (Osteosarc n.d.-f, 1, 13).
- **TP53 at T0 remains unresolved in the DRAGEN report.** Although the overview calls TP53 LOH truncal, the detailed CNV page says the T0 segment is absent from the PASS set and recommends checking the underlying evidence. Do not record TP53 LOH as established at T0 (Osteosarc n.d.-b, n.d.-a).
- **HRD remains discordant.** The score of 45 and CHORD probability of 0.014 are distinct outputs. The signature report also assigns about 23% to Sig3, but that does not resolve the discrepancy or establish treatment sensitivity (Osteosarc n.d.-d, n.d.-g).
- **Long telomeres are suggestive, not an ALT diagnosis.** TEAL estimates approximately 19.8 kb in T0 tumor, roughly 16 times matched normal. The site itself raises a possible library/normalization effect (Osteosarc n.d.-l).
- **Negative report categories have limited scope.** ORANGE reports no germline driver variants and no driver fusions; this does not exclude every inherited predisposition or every rearrangement (Osteosarc n.d.-f, 3, 5).

The ORANGE report is explicitly for research use. No clinician-confirmed driver conclusion is established by the reviewed sources (Osteosarc n.d.-f).

## Works Cited

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-a. “DRAGEN Somatic Analysis.” Accessed September 25, 2026. https://osteosarc.com/dragen/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-b. “DRAGEN Somatic — Copy Number.” Accessed September 25, 2026. https://osteosarc.com/dragen/cnv/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-c. “DRAGEN Somatic — QC.” Accessed September 25, 2026. https://osteosarc.com/dragen/qc/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-d. “DRAGEN vs oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/comparison/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-e. “Drivers — oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/drivers/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-f. “HMF ORANGE Report v4.1.2: IPISRC044_tumor_T0_personalis.” Pipeline version 2.3. Research-use-only report, 17 pp. Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/orange/personalis.orange.pdf.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-g. “Mutational Signatures — oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/signatures/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-h. “oncoanalyser — Sid's Data.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-i. “Osteosarcoma Xenium — Analysis & Interpretation.” Accessed September 25, 2026. https://osteosarc.com/xenium/analysis/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-j. “PARD3B :: CDKN2B-AS1/CDKN2B — Fusion Evidence.” Accessed September 25, 2026. https://osteosarc.com/fusions/pard3b--cdkn2b-as1-cdkn2b/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-k. “SNV / Indel — oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/snv/.

Osteosarc (Sid Sijbrandij's Osteosarcoma Data). n.d.-l. “Telomeres — oncoanalyser.” Accessed September 25, 2026. https://osteosarc.com/oncoanalyser/telomeres/.
