---
title: "Dataset specification"
description: >-
  Defines the authoring contract for curated dataset specifications documenting a bounded dataset asset used for AI training, fine-tuning, evaluation, analytics, or engineering reuse beyond single-campaign test fixtures. Covers dataset identity, immutable snapshot bindings, intended and prohibited uses, record composition, schema and split-leakage rules, collection or synthetic-generation provenance, preprocessing steps, conditional annotation protocols and label-quality metrics, licensing, consent, and privacy safeguards, known biases and limitations, maintenance and takedown policies, and conditional bindings to validated machine-readable dataset metadata descriptors.
topics:
  - "specifications"
  - "data-engineering"
  - "ai-and-ml"
  - "dataset-specification"
  - "data-provenance"
  - "dataset-composition"
  - "annotation-protocol"
  - "data-bias"
use_when:
  - "A curated, collected, or synthetically generated dataset for AI training, evaluation, or analytical reuse needs comprehensive provenance, composition, and governance documentation."
  - "A data steward or ML engineer is recording exact snapshot digests, split-leakage prevention, annotation quality, licensing, privacy limits, and known biases."
  - "A reviewer is verifying whether a dataset is legally, ethically, and statistically suitable for a proposed modeling, evaluation, or analytical task."
not_for:
  - "Defining reproducible test-only input fixtures and suitability checks for a bounded software or system test campaign, which belongs in a test data specification."
  - "Governing ongoing producer-to-consumer operational stream or table schemas, freshness SLAs, and compatibility rules, which belongs in a data contract specification."
  - "Disclosing an AI model or compound AI system's overall architecture, capabilities, and oversight constraints, which belongs in an AI model or system card."
  - "Preserving raw qualitative transcripts and provenance from user discovery interviews, which belongs in an elicitation and source record."
---

# Dataset specification

## Identity and selection

- **Specification ID:** `DATASET-SPECIFICATION@core`.
- **Purpose:** Define a curated, collected, or synthetically generated dataset asset—covering its identity, snapshot provenance, composition, preprocessing, labeling methodology, rights, privacy safeguards, known biases, and maintenance lifecycle—so consumers can evaluate suitability and reproduce exact dataset editions.
- **Intended readers:** Machine-learning and data engineers, researchers, evaluation leads, dataset stewards, privacy and legal reviewers, and downstream consumers.
- **Decision or action supported:** Judge whether the dataset is technically, statistically, legally, and ethically fit for training, fine-tuning, evaluation, or analytics; verify snapshot integrity; and account for labeling error, split leakage, and sampling biases.
- **Use when:** A dataset asset is created, curated, released, or consumed for AI/ML development, empirical benchmarking, or reusable analytical work beyond narrow single-campaign test fixtures.
- **Scope boundaries:** Specify one coherent dataset asset and its versioned snapshot, provenance, composition, labeling, rights, biases, and lifecycle; exclude ongoing producer-consumer operational data-product SLAs, narrow test-campaign input specifications, raw user-research transcripts, and legal clearance certifications.

## Authoring inputs and unresolved facts

Obtain the dataset identity, edition or version, materialization state, immutable snapshot locator and cryptographic digest when materialized, accountable creator or steward role, intended uses, and explicitly discouraged or prohibited uses; record granularity, modalities, file formats, structural schema, total and per-split instance counts, splitting and deduplication rules preventing cross-split leakage, and observed summary statistics bound to the exact snapshot; raw sources and upstream dataset editions, collection or synthetic-generation methods (including generator model versions and prompts when synthetic), sampling criteria, filtering, cleaning, and transformation pipelines; when labels or ratings exist, the annotation taxonomy, guideline edition, annotator qualifications or automated-labeling model, quality checks, adjudication rules, and measured inter-annotator agreement or noise estimates; intellectual-property ownership, licenses, redistribution terms, consent or collection-authority basis, personal or sensitive data presence, de-identification methods actually applied with known residual limits, access controls, and retention or takedown routes; known sampling skews, domain or temporal gaps, content errors, benchmark-contamination risks, update policy, and issue-reporting channel; and for any selected machine-readable dataset metadata descriptor (such as Croissant JSON-LD or Frictionless Data Package), its schema, version, locator, mapping, validator, and check status.

If an upstream source, collection authority, license, consent basis, snapshot digest, split-deduplication check, annotator agreement, or privacy redaction verification is unknown or unperformed, expose that gap explicitly with its suitability consequence, resolving action, and actual owner only when assigned. Do not present planned collection targets as observed dataset statistics, label partially redacted personal data as anonymous without evidence, assume upstream third-party datasets carry commercial redistribution rights, or embed raw personal or protected sample records into the specification. Unresolved licensing, consent, or privacy protection blocks claiming the dataset is cleared for training, distribution, or external release.

## Finished-document contract

- **Title:** Name the dataset and its covered version or snapshot edition and identify the document as its dataset specification.
- **Frontmatter:** Required on standalone GFM documents; omitted on selected machine-readable native dataset metadata descriptors or schema manifests whose formats manage metadata natively. Begin standalone GFM documents with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), excluding internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values, followed by the H1 title. Dataset version, snapshot integrity, provenance, rights, and descriptor check status belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract and this type's projection policy.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish dataset identity, snapshot, and intended uses before composition and provenance; place conditional annotation methodology before rights, privacy, known biases, maintenance lifecycle, and any native descriptor binding. Heading wording may vary.
- **Presentation:** Scale schema tables, split summaries, and transformation logs to the dataset's complexity without adding empty annotation chapters for unlabeled corpora. Required roles may share sections while keeping snapshot bindings, split-leakage rules, provenance gaps, rights boundaries, and bias disclosures immediately retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Dataset specification document (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one dataset-specific H1. Dataset version, immutable snapshot locator and digest, composition observations, rights basis, and corpus-level governance inheritance where applicable remain body content. | Use GFM prose and summary tables grounded in the exact inspected dataset snapshot and provenance records. Actual dataset files remain controlling for raw records; regenerating, filtering, relabeling, or updating splits creates a new edition requiring specification reassessment. |
| Native dataset metadata descriptor (native) | A machine-readable dataset metadata descriptor (such as Croissant JSON-LD, Frictionless Data Package, or registry manifest) omits Semantic-Discovery YAML frontmatter and retains its format-native schema properties without injected Markdown headings. | The declared metadata specification and version govern native syntax and validation rules. Validator status applies solely to the checked descriptor artifact, schema version, and mapping; GFM prose does not establish descriptor validity, and snapshot changes require re-validation. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Dataset identity, snapshot, and intended use | Required | Identify the dataset, version or edition, materialization state (`planned`, `materialized`, `deprecated`, or `withdrawn`), immutable storage locator and content digest when materialized, modalities, accountable creator or steward, primary intended uses (such as training, fine-tuning, evaluation, or analytics), explicitly discouraged or prohibited uses, exclusions, and the client or receiving-party element when applicable. |
| Composition, structure, and statistical profile | Required | Define what one instance or record represents, file format and structural schema, total and per-split record counts (train, validation, test, or holdout), splitting and deduplication strategy preventing cross-split or entity leakage, label or attribute distributions, missing-value characteristics, and temporal, geographic, or linguistic coverage measured on the exact snapshot. |
| Provenance, collection, and preprocessing | Required | Document raw data sources and upstream dataset editions, acquisition or synthetic-generation methods (naming generator models, versions, prompts, and seeds when synthetic), sampling strategy, inclusion and exclusion filters, deduplication, cleaning, normalization, and transformation pipeline versions needed to interpret or reproduce the dataset. |
| Annotation and labeling methodology | Conditional when the dataset includes human, automated, or hybrid labels, ratings, or ground-truth annotations | Specify the label taxonomy and guideline edition, annotator recruitment, qualifications, or automated-labeling model and version, quality-control checks, conflict-adjudication rules, and observed inter-annotator agreement or error-rate measurements with sample scope. State explicitly when the dataset is unlabeled in Dataset identity, snapshot, and intended use. |
| Rights, privacy, and ethical governance | Required | State ownership, applicable licenses and redistribution or derivative-work terms, consent or lawful-collection basis, presence of personal, confidential, or sensitive attributes, de-identification or redaction techniques actually applied with residual re-identification limits, access controls, and retention, opt-out, or takedown procedures. Distinguish unknown rights from cleared use. |
| Known limitations, biases, and maintenance lifecycle | Required | Expose sampling skews, underrepresented populations or domains, temporal staleness, known label noise or content defects, evaluation-contamination risks, versioning and update rules, deprecation or withdrawal criteria, issue-reporting channel, and accountable maintenance role. |
| Native metadata descriptor binding | Conditional when one or more machine-readable dataset metadata descriptors or schema manifests are selected | For each selected native descriptor, identify format and version, controlling artifact locator, mapping to human specification fields, validator tool, and actual check status (`pass`, `fail`, `inconclusive`, or `not-run`). Preserve unmapped fields explicitly and require re-checking on any snapshot or descriptor change. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Dataset identity and snapshot | Exactly one dataset identity, version, materialization state, and immutable snapshot binding (when materialized) in Dataset identity, snapshot, and intended use. | Include exact locator and content digest or manifest checksum for materialized snapshots; planned datasets remain visibly unmaterialized without fabricated hashes. |
| Intended and prohibited use | One or more intended uses and one or more discouraged or prohibited uses in Dataset identity, snapshot, and intended use. | Bound downstream reuse (such as training versus evaluation-only or non-commercial limits) explicitly so consumers do not misuse the asset. |
| Split and leakage rule | One coherent splitting and deduplication account in Composition, structure, and statistical profile. | State split ratios, grouping keys (such as user, document, or temporal cutoff), deduplication method, and whether cross-split leakage checks were actually performed. |
| Composition statistic | One observed profile covering counts, formats, distributions, missingness, and coverage in Composition, structure, and statistical profile. | Bind every figure to the exact materialized snapshot; label planned target counts separately from observed measurements. |
| Provenance and transformation step | One or more sourced origin and preprocessing accounts in Provenance, collection, and preprocessing. | Identify upstream editions, collection timeframes, synthetic generator versions if applicable, and filtering criteria that materially alter distribution. |
| Annotation and quality record | Conditional on Annotation and labeling methodology being included; one account per labeling scheme. | State guideline edition, labeler type (human, model, hybrid), quality checks, and measured agreement or error rate with sample size; mark unmeasured label noise explicitly. |
| Rights and privacy disposition | One rights, licensing, consent, and privacy-protection account in Rights, privacy, and ethical governance. | Separate observed license text and legal review from unverified assumptions; masking identifiers alone does not establish anonymization. |
| Bias and limitation account | One or more documented skews, gaps, contamination risks, or known defects in Known limitations, biases, and maintenance lifecycle. | State concrete impact on modeling or evaluation interpretation; assessed absence of a specific bias requires naming the check performed. |
| Maintenance and takedown policy | One stewardship, versioning, and withdrawal account in Known limitations, biases, and maintenance lifecycle. | Name accountable steward, issue-reporting route, update rules, and how takedown or erasure requests affect published snapshots. |
| Native metadata descriptor | Zero or more bound machine-readable metadata files in Native metadata descriptor binding. | Each entry binds format, version, artifact locator, mapping, validator, and check outcome; checks do not transfer across formats or dataset versions. |

Use structured tables for schema fields, per-split composition counts, upstream provenance sources, and native descriptor bindings, paired with concise prose for collection methodology, privacy safeguards, and known biases. Cite separate annotation guideline documents or processing repositories by exact edition and locator rather than embedding lengthy labeling manuals or raw sample records containing personal data. Do not insert blank rows, placeholder hashes, or unsupported legal-clearance assertions.

## Quality criteria

- Dataset identity, version, materialization state, snapshot integrity binding, and intended versus prohibited uses are unambiguous and grounded in actual records.
- Composition statistics, split definitions, and leakage-prevention checks match the exact materialized snapshot rather than planned collection estimates.
- Provenance accounts expose all material upstream editions, synthetic-generation configurations when applicable, and filtering steps that shape dataset distribution.
- Labeled datasets define their taxonomy, labeling method, adjudication, and measured agreement or expose unmeasured label quality explicitly; unlabeled datasets state that scope clearly.
- Licensing, consent basis, personal-data presence, applied redaction limits, and takedown routes are traceable; unresolved rights or privacy gaps visibly block cleared-use claims.
- Known biases, domain gaps, contamination risks, and maintenance or withdrawal rules are concrete enough to inform downstream modeling or evaluation interpretation.
- Any bound machine-readable metadata descriptor states its format, version, artifact locator, mapping, validator, and actual check status without relying on GFM prose for schema conformance.
