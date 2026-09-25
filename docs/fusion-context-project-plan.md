# Fusion Partner Context: a three-hour Codex project

Date: 2026-09-25  
Status: implementation plan; analysis has not been executed.  
Team: 2–3 people. Primary deliverable: a reusable agent-callable tool.  
Companion input specification: [fusion-context-data-manifest.json](fusion-context-data-manifest.json).

## Objective and scope

Build a reproducible tool that takes one gene pair and presents three views: existing T0/T1 rearrangement evidence, partner expression in T1 single-cell RNA, and partner protein abundance across T0 spatial proteomics regions. A second pair is a stretch goal after the first complete report works.

The scientific question is: **Where are the partners of a reported rearrangement expressed in the available cellular and tissue contexts?** The project practices two modalities while producing a reusable evidence-reporting tool.

T1 RNA and T0 proteins are different specimens and timepoints. Their juxtaposition does not establish temporal change, fusion-bearing cells, fusion protein expression, or an RNA–protein correlation. Partner expression is contextual evidence, not fusion validation.

Use existing processed data and annotations. No alignment, fusion calling, new clustering, cell annotation model, differential expression, raw mass-spectrometry processing, or clinical interpretation is required.

## Candidate selection

Start provisionally with the site's PARD3B–CDKN2B-AS1/CDKN2B candidate (Osteosarc n.d.-b). Preserve its original ambiguous label. Treat PARD3B, CDKN2B-AS1, and CDKN2B as distinct features; never substitute CDKN2B protein for the antisense transcript.

At minute 45, lock one candidate based on an existing report, interpretable gene mapping, and available expression/protein coverage. Prefer at least one unambiguously mapped partner protein to exercise the spatial view. If another reported pair has better coverage, record why it was selected. This is demonstration-driven selection, not evidence of biological importance. Add a second pair only after the complete first report passes validation.

## Required data and readiness

The JSON manifest lists only the necessary input roles and mutually exclusive RNA input routes. URLs are acquisition candidates, not proof of a completed download.

| Input | Source and current knowledge | Execution check |
| --- | --- | --- |
| Candidate evidence | Selected fusion report; retain T0/T1 rows and original assay/library identifiers | Snapshot relevant evidence with source URL; do not pool duplicate alignments as independent reads |
| T1 annotated scRNA | Catalog lists a T1 Seurat RDS, approximately 969 MB; an alternative analyzed h5ad is listed under Kamil's analysis | Select one route; inspect expression layers, feature identifiers, cell annotations and sample labels |
| T0 protein groups | Exact object: vendor/resolute.bio/T0_B1_pg_matrix.tsv | Verify identifiers, numerical representation and join to region metadata |
| T0 region metadata | Exact object: vendor/resolute.bio/T0_B1_metadata.tsv | Join sample_id; keep filter_stage == analyzed |
| Spatial data dictionary | vendor/resolute.bio/README.md, retrieved during planning | Preserve source semantics and a checksum |

The Resolute README documents 7,979 protein-group rows, 247 measured regions, 232 QC-passing regions, and WKT region outlines in level-0 image pixels. These coordinates permit a region map without the whole-slide image (Resolute Bio n.d.). Matrix and metadata contents still need execution-time validation.

The T1 RDS is the most specific cataloged RNA input. Prefer it if R/Seurat is already available. Otherwise inspect the listed h5ad route and retain only verified T1 cells. Its filename alone does not establish timepoint or annotation coverage. Do not download both routes speculatively (Osteosarc n.d.-a).

## ClawBio integration

ClawBio skills may supply analysis components. Inspect the current skill catalog and pin the repository commit before use. Candidate skills to assess are scrna-orchestrator and proteomics-de, which are listed in the repository. Their exact contracts and suitability must be checked at kickoff; this plan does not assert support for a processed-object summary mode or spatial plotting (ClawBio n.d.).

Read a selected skill's SKILL.md and relevant code before invoking it. Use only components compatible with preserving existing annotations, expression semantics, and protein missingness. Do not run a complete QC/clustering or differential-expression workflow merely to use a skill. In particular, spatial regions are not independent biological replicates for a T0-versus-T1 test.

Budget at most ten minutes within the initial access gate for skill compatibility and dependency checks. If a compatible component is readily callable, use it and record the skill path, commit, command, and outputs. Otherwise use small Python/Scanpy/pandas adapters and document the reason. No OpenClaw server, chat integration, GPU, or external model API is required. A thin reusable skill wrapper can be added after the CLI works; ClawBio packaging is not a completion requirement.

## Three-hour execution schedule

| Elapsed minutes | Work | Required result |
| --- | --- | --- |
| 0–25 | Check repository instructions, runtime and ClawBio compatibility; fetch small protein inputs; start exactly one RNA route | discovery.md with accessibility, schema findings, download status and blockers |
| 25–45 | Finish loading; verify T1 selection, RNA layers and protein coverage; choose primary candidate | Resolved manifest, field mapping and locked candidate |
| 45–110 | Implement RNA and spatial-protein adapters, then numeric summaries | Both modalities produce validated intermediate results |
| 110–145 | Join evidence by candidate identity; generate report and provenance | Complete first report; feature freeze |
| 145–170 | Validate numeric examples and missingness; rerun from recorded command | Reproducible output and focused checks |
| 170–180 | Prepare short demo and handoff | README, final artifacts and honest completion status |

With three people: one owns evidence/manifest and integration, one RNA, one spatial proteins. With two: one owns RNA, the other proteins; share final integration. Human work can overlap. Codex can execute the same milestones sequentially without autonomous agent delegation.

**Data gate:** at minute 25, abandon any route requiring a long installation or unresolved bulk acquisition. Switch once to an already accessible alternate RNA route if feasible. At minute 45, if either real modality remains unavailable, deliver a clearly labeled partial tool/report with the exact blocker. Synthetic fixtures may test interfaces but must never appear as biological results. Do not silently replace spatial proteins or scRNA with another modality.

## Analysis contract

### 1. Evidence adapter

Curate only the selected candidate's relevant report rows. Store candidate_id, original label, source URL, access date, timepoint, assay, source sample/library identifier and reported support. Preserve unavailable values as null. Keep reported DNA and RNA evidence distinct. Do not infer clinician validation from a public analytical report.

### 2. Single-cell RNA adapter

Select T1 cells using validated metadata or documented T1-only object provenance. Preserve supplied cell-type labels; if only clusters exist, label the output as clusters and record the limitation. Do not invent malignant-cell labels.

Resolve gene symbols/IDs explicitly, recording unmapped and duplicate mappings. Retain all selected cells, including zero-expression cells. For each partner and cell group, output total cells, cells with detectable expression, fraction detected, and mean expression on a named scale.

Detection requires raw counts or a documented nonnegative expression representation preserving zeros. Scaled or integrated values cannot support a count-positive detection rule. If only counts exist, compute library-size normalization over the complete measured gene set before subsetting partners; never normalize using only the selected genes. If required semantics are unknown, mark the affected metric unavailable rather than guessing.

Use an existing normalized layer when its meaning is documented. State its transformation in tables and plots. A dot plot is sufficient; an existing embedding is optional and must not trigger a new embedding computation.

### 3. Spatial-protein adapter

Read Protein.Group, Protein.Ids, Protein.Names and Genes as identifiers and join remaining region columns to metadata sample_id. Check uniqueness and unmatched IDs. Filter the analysis set to filter_stage == analyzed; retain excluded-region counts in provenance.

Match complete gene tokens rather than substrings. Preserve ambiguous protein groups and do not duplicate their intensity across genes or sum them into an apparently specific protein measurement. Missing abundance remains missing, not zero. Keep source units; apply a log transform only when its validity is established and label it explicitly. Do not impute or run differential abundance testing.

Draw the supplied WKT polygons colored by partner-associated protein-group abundance. Preserve image pixel coordinates, equal axis scaling and image orientation; label the map as tissue regions without a histology background. Do not assign tumor/immune compartment labels without supplied annotation. If geometry parsing cannot be completed within the timebox, retain a region heatmap and mark the spatial-map output incomplete.

### 4. Report

Produce a standalone HTML report plus machine-readable JSON and a Markdown summary. Include candidate provenance, separate T1 RNA and T0 protein panels, data coverage, mapping ambiguity, missingness, exclusions and limitations. Every modality plot must display its timepoint.

Allow switching between partners and, if implemented, pairs. Keep calculations in deterministic analysis code; narrative text must refer to those computed results. No cross-timepoint statistical test, inferred cell-to-region matching, or combined evidence score is needed.

## Implementation specification

Implement one adapter per chosen source format, not a general data platform. Suggested modules: io.py, scrna.py, proteomics.py, report.py and cli.py under fusion_context/. A config file maps actual upstream fields and layers to the logical contract.

Proposed commands to implement (these do not exist yet):

~~~bash
python -m fusion_context inspect --manifest docs/fusion-context-data-manifest.json --out results/preflight
python -m fusion_context run --manifest results/preflight/resolved-manifest.json --config config/project.json --out results/demo
~~~

The resolved manifest must include actual local paths, source URLs, byte sizes, SHA-256 checksums, selected RNA route, actual schema mappings, layer semantics and filtering rules. Validate required roles before analysis. Unresolved inputs must produce a non-success status for a full run.

Use an isolated, recorded environment with only needed dependencies. Keep raw inputs and large objects out of git. Save code, configuration, selected small summaries and reproducibility instructions in the project repository. Resume existing work without overwriting unrelated changes.

## Acceptance criteria and focused validation

A full MVP requires one real candidate, real T1 RNA summaries, real T0 protein-region results, traceable source evidence, and one repeatable command. Both modalities must load and pass their input checks. Missing candidate features are legitimate findings and must be labeled; the preferred demo includes a detected, unambiguously mapped protein partner.

Verify these specific risks with small synthetic fixtures: correct T1 filtering; detection denominators include zeros; normalization uses full-cell library totals; absent features differ from zero expression; missing protein values remain missing; ambiguous protein mappings remain explicit; RNA and protein timepoints cannot be silently merged.

For the real run, independently recompute one RNA group summary and one protein-region value, check region joins/QC counts against the data dictionary, and confirm report values match the JSON. Render/open the report once to inspect labels and missing-value display. Stop testing once these concrete risks are covered.

Completion levels:
- **Complete:** both real modalities and a valid spatial map, with reproducibility and provenance.
- **Complete analysis, reduced visualization:** both real modalities, but region heatmap replaces geometry map.
- **Partial:** a real modality or its required semantics is unavailable; blocker documented, never represented as a complete multimodal result.

## Deliverables

1. Reusable CLI and source adapters, with optional ClawBio/agent wrapper.
2. Resolved minimal manifest and source-field configuration.
3. Standalone HTML report, JSON evidence/results, Markdown summary and small plot artifacts.
4. README with exact invocation, dependency lock/version record, checksums, limitations and a two-minute demo script.
5. Focused validation results and explicit completion status.

Stretch work, only after the first complete report: second pair, existing RNA embedding, or polished skill packaging. Whole-slide overlays and additional modalities are outside the three-hour scope.

## Codex kickoff instruction

> Read this plan, its JSON manifest and applicable repository instructions. Implement the one-pair MVP within the 180-minute schedule. Begin with the data/ClawBio compatibility gate and record findings. Select exactly one RNA acquisition route; validate its sample labels and expression semantics. Use compatible ClawBio components when available without expanding the analysis. Preserve T1 RNA and T0 proteins as separate contextual evidence. Do not infer fusion-bearing cells or fusion protein from partner abundance. Produce real-data results only from inspected inputs, report hard blockers honestly, and finish with reproducible artifacts and focused validation.

## Works cited

ClawBio. n.d. “ClawBio.” GitHub repository. Accessed September 25, 2026. https://github.com/ClawBio/ClawBio.

Osteosarc. n.d.-a. “Data.” Accessed September 25, 2026. https://osteosarc.com/data/.

Osteosarc. n.d.-b. “PARD3B–CDKN2B-AS1/CDKN2B.” Accessed September 25, 2026. https://osteosarc.com/fusions/pard3b--cdkn2b-as1-cdkn2b/.

Resolute Bio. n.d. “Resolute Bio — Spatial Proteomics.” Dataset README. Retrieved September 25, 2026. https://sid-sijbrandij-osteosarc-dataset.s3.us-west-2.amazonaws.com/vendor/resolute.bio/README.md.
