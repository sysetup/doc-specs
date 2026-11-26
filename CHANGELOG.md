# Changelog

Notable changes to this collection are recorded here, following
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
One project version governs the entire collection.

## 3.2.0

Released 2026-11-23. Expanded the collection to 153 specifications by adding 9 modern engineering, reliability, data, privacy, and AI document specifications, refactoring adjacent sibling boundaries, and extending the controlled domain topic taxonomy compatibly.

### Added

- `AI-EVALUATION-REPORT@core`: Preserve empirical AI model or compound AI system evaluations covering evaluated snapshots, benchmark and red-team suites, contamination disclosures, judge calibration, uncertainty, disaggregated slices, and bounded conclusions.
- `AI-SYSTEM-CARD@core`: Disclose an AI model or compound AI system's identity, maturity, intended and out-of-scope uses, system composition, data provenance summaries, cited evaluation results, human oversight, operational limits, and optional native registry exports.
- `CAPACITY-PLAN@core`: Plan workload demand forecasts, empirical baselines, resource headroom targets, scaling cliffs, provisioning lead times, cost envelopes, and load validation across a declared horizon.
- `DATA-CONTRACT@core`: Govern producer-to-consumer schemas, field semantics, data quality and freshness guarantees, privacy classifications, schema-evolution compatibility, deprecation rules, and optional native schema artifacts.
- `DATASET-SPECIFICATION@core`: Specify curated dataset assets covering immutable snapshot bindings, intended and prohibited uses, composition and split-leakage rules, collection or synthetic provenance, conditional annotation quality, licensing, privacy safeguards, known biases, and optional native metadata descriptors.
- `DPIA@core`: Assess personal-data processing necessity, data flows, data-subject rights mechanisms, individual privacy risks, technical and organizational safeguards, consultations, residual risk, and processing dispositions.
- `SLO-SPECIFICATION@core`: Define measurable service level indicators, service level objectives, compliance windows, derived error budgets, burn-rate alerting tiers, error-budget exhaustion policies, and optional native SLO manifests.
- `TECHNICAL-RFC@core`: Circulate pre-decision technical design proposals for peer review, alternatives evaluation, cross-cutting impact analysis, migration planning, objection tracking, and explicit disposition.
- `THREAT-MODEL@core`: Maintain living adversarial threat models decomposing protected assets, attack surfaces, data flows, and trust boundaries into threat scenarios, mapped mitigations, verification status, residual exposure, and reassessment triggers.
- Added 3 compatible controlled domain topics (`ai-and-ml`, `data-engineering`, `privacy-and-compliance`) to `CONTRIBUTING.md` (`FM-01`), bringing the shared controlled taxonomy to 25 tags.

### Changed

- Updated the single project version to `3.2.0` and synchronized collection count (`153`) across `CONTRIBUTING.md`, `authoring/families.json`, `authoring/request.template.json`, `INDEX.csv`, `CATALOG.json`, `README.md`, `llms.txt`, and `CHANGELOG.md`.
- Refactored `not_for` exclusions and adjacent `Scope boundaries` across 24 neighboring sibling specifications (`SECURITY-ENGINEERING-PLAN@conditional`, `RISK-REGISTER@core`, `HAZARD-LOG@core`, `FMEA@core`, `VULNERABILITY-RECORD@core`, `AVAILABILITY-PLAN@core`, `OPERATIONS-PLAN@core`, `OBSERVABILITY-REGISTER@core`, `SERVICE-STATUS-REPORT@core`, `RUNTIME-ENVIRONMENT-SPECIFICATION@core`, `INTERFACE-CONTROL@core`, `TEST-DATA-SPECIFICATION@core`, `TECHNICAL-REFERENCE@core`, `CONTROL-IMPLEMENTATION-RECORD@core`, `RESEARCH-PARTICIPANT-INFORMATION@core`, `ADR@core`, `TRADE-STUDY-REPORT@core`, `CHANGE-REQUEST@core`, `ARCHITECTURE-DESCRIPTION@core`, `PRODUCT-GUIDE@core`, `VERIFICATION-EVIDENCE@core`, `VALIDATION-EVIDENCE@core`, `TECHNICAL-ANALYSIS-REPORT@core`, and `TEST-COMPLETION-REPORT@core`) to preserve clean selection boundaries.

## 3.1.0

Released 2026-11-23. Unified the entire 144-specification collection under one project version and full structural conformance across all families, catalogs, and authoring resources.

### Added

- Added derived Tier-2 discovery catalog `CATALOG.json` combining family metadata, catalog summaries, faceted `topics`, `use_when`, `not_for`, and projection kinds (`standalone`, `native`) with lexicographically sorted keys for single-read agent filtering.
- Added controlled shared domain topic taxonomy (22 cross-cutting lowercase `kebab-case` tags) in `CONTRIBUTING.md` (`FM-01`) and applied faceted shared plus specific topics across all 144 specifications.
- Added `- **Presentation:**` guidance and `Projection` tables (`STR-05`) to the 136 specifications that previously lacked them, plus dual-surface native projections for `THIRD-PARTY-NOTICES@core` and `CONTRACTED-WORK-AGREEMENT@core`.
- Added `- **Scope boundaries:**` to the 10 specifications missing that identity bullet (`GUIDE@core`, `POLICY@configuration-management`, `POLICY@cybersecurity`, `POLICY@engineering`, `POLICY@quality`, `POLICY@risk-management`, `ACTION-ITEM-REGISTER@core`, `ADR@core`, `ASSET-REGISTRY@it`, `ASSUMPTION-DEPENDENCY-REGISTER@core`).
- Added repository line-ending and editor safeguards (`.gitattributes` preserving exact CRLF bytes for `*.csv` and enforcing LF for Markdown/JSON/text files, `.editorconfig`, and `.gitignore`).

### Changed

- Unified versioning under single project version `3.1.0` across `CONTRIBUTING.md`, `authoring/families.json`, `authoring/request.template.json`, `authoring/specification.template.md`, `CATALOG.json`, `README.md`, `llms.txt`, and `CHANGELOG.md`, removing separate per-file `Specification edition` bullets and `(standard 3.0.0)` body couplings across all 144 specifications.
- Aligned `CONTRIBUTING.md`, `authoring/request.template.json`, and `authoring/specification.template.md` for deterministic composition: removed the unused optional metadata-field table (former Block 8a) and redundant `fields` array, defined exact `Frontmatter` rendering formulas for `required` and `conditional` policies, enforced `"specification"` title deduplication consistently, defined ASCII whitespace word counting in `FM-01`, relaxed `STR-03` to allow additional domain note paragraphs, ordered rule identifiers sequentially (`SEL-01`–`SEL-06`, `STR-01`–`STR-11`), and generalized uniform corpus-level governance inheritance across all applicable families.
- Replaced external numbered frontmatter-purity labels with local frontmatter semantic purity (`FM-02`) across all specifications, templates, and entrypoints.
- Synchronized titles across `INDEX.csv`, frontmatter `title`, and H1 headings for `VV-PLAN@combined` (`Combined verification and validation plan specification`) and all six `DESIGN-REVIEW@*` variants (`record` suffix in `INDEX.csv`).
- Normalized all 22 non-conforming role-table status cells across 17 specifications to strict `STR-06` syntax (`Required`, `Optional`, or `Conditional when <predicate>`).
- Decoupled `TASK-EXECUTION-PLAN@core` from host-specific `AGENTS.md`, `PLAN.md`, and `04-control` references so the specification remains environment-agnostic.
- Clarified dual-surface native export frontmatter rules in `SECURITY-ADVISORY@core`.
- Sorted object keys lexicographically in `authoring/families.json` and normalized typography (straight ASCII quotes and angle-bracket title placeholders) across affected specifications and `CONTRIBUTING.md`.

### Removed

- Removed legacy format exemptions from `CONTRIBUTING.md` and per-specification `Specification edition` lines from all 144 specifications.

## Release 2026-11-23

This declared breaking major release includes all 144 catalog specifications upgraded to authoring standard `3.0.0`, the compact RFC 4180 discovery catalog `INDEX.csv`, both authoring templates, and the family registry. Authoring standard `3.0.0` is released, adopted, and effective from this collection release.

### Added

- Added standardized 5-key Semantic-Discovery YAML frontmatter (`title`, `description` 60–140 neutral words, `topics` 3–12, `use_when` 2–6, and conditional `not_for` 1–5) to all 144 catalog specifications for three-tier agent discovery.
- Added compact RFC 4180 `INDEX.csv` (`family,type,title,path,summary`, UTF-8 without BOM, CRLF terminators, sorted deterministically by family registry order and relative path) indexing all 144 specifications.

### Changed

- Released and adopted breaking major specification authoring standard `3.0.0` (`CONTRIBUTING.md`, `authoring/specification.template.md`, `authoring/request.template.json`): mandated 5-key Semantic-Discovery YAML frontmatter and semantic purity on every specification file and standalone Markdown finished document, defined maintenance rules for `INDEX.csv`, decoupled inline specification provenance when bound externally, sorted JSON request template keys lexicographically, and standardized compact GFM table delimiters (`| --- |`).
- Updated all 144 catalog specifications to replace every legacy no-frontmatter finished-document directive with the mandatory 5-key Semantic-Discovery YAML frontmatter requirement (preserving native-surface metadata rules for dual-surface types), align standalone projection rows, decouple inline provenance in `TASK-EXECUTION-PLAN@core`, and normalize compact GFM table delimiters.
- Updated `README.md` and `llms.txt` to reflect Release `2026-11-23`, authoring standard `3.0.0`, `INDEX.csv`, three-tier progressive disclosure, and repository Markdown conventions.

## Release 2026-11-21

This declared release includes all 144 catalog specifications, authoring standard 2.1.0, both authoring templates, and the family registry. Authoring standard 2.1.0 is released, adopted, and effective from this collection release.

### Added

- `TASK-EXECUTION-PLAN@core`: Maintain the current state of one bounded task for durable tracking, recovery, and handoff.

### Changed

- Released and adopted specification authoring standard 2.1.0 (`CONTRIBUTING.md`, `authoring/specification.template.md`, `authoring/request.template.json`) as a backward-compatible minor update over 2.0.0: made the shared `Client or receiving party` clause strictly conditional (omit for internal documents unless a specific project policy requires explicit negative attestation) and recognized corpus-level versioning (`CHANGELOG.md` plus Git revision) and declared catalog/corpus default maintainers for unified operational corpora.
- Updated all 144 catalog specifications (including aligning `TASK-EXECUTION-PLAN@core` with the shared literal contract) to apply the strictly conditional `Client or receiving party` rule.
- Clarified corpus-level version and catalog/corpus default maintainer inheritance in core governance, process, interface, and task-plan specifications (`STANDARD@core`, `POLICY@core`, `POLICY@configuration-management`, `POLICY@cybersecurity`, `POLICY@engineering`, `POLICY@quality`, `POLICY@risk-management`, `GUIDE@core`, `SOP@core`, `RUNBOOK@core`, `WORK-INSTRUCTION@core`, `INTERFACE-CONTROL@core`, and `TASK-EXECUTION-PLAN@core`).
- Updated `README.md` to describe the actual repository contents, link automated-reader and license resources, reflect Release 2026-11-21 and authoring standard 2.1.0, and remove the obsolete three-tree installation convention and dedicated operational proposal-directory workflow.
- Aligned `llms.txt` with Release 2026-11-21, authoring standard 2.1.0, and the repository's documentation scope and ownership of finished documents and operational instructions.
- Corrected the editorial reference in authoring standard 2.0.0 to removed `A01–A23` supporting material.

### Removed

- Retired the previously unreleased `DOCUMENT-AUTHORING-PROFILE@host` specification (`04-control/document-authoring-profile--host.spec.md`) prior to release and removed its catalog entry; centralized host authoring defaults are governed through `STANDARD@core` or owning project standards.

## Release 2026-10-06

This declared release includes all 143 catalog specifications and the authoring standard 2.0.0, both authoring templates, and the family registry. The authoring standard is released, adopted, and effective from this collection release.

### Added

- An authoritative family registry in `authoring/families.json`, retaining the six existing responsibilities and their order.
- `CHANGELOG@core`: Maintain a meaningful history of changes across established versions and separately identified pending work.
- `CONTRACTED-WORK-AGREEMENT@core`: Control the terms, parties, revisions, and decision state of contracted study, development, or maintenance commitments.
- `ELICITATION-INSTRUMENT@core`: Define the questions, prompts, observation cues, and capture rules used to collect information.
- `ELICITATION-RECORD@core`: Preserve actual elicitation statements, observations, and raw-source provenance before interpretation.
- `ENGINEERING-EFFORT-RECORD@core`: Record engineering effort actually consumed and its attribution, units, source, and correction basis.
- `ENGINEERING-STATUS-REPORT@core`: Report bounded engineering delivery progress, impediments, resource facts, and forecast.
- `MEETING-RECORD@core`: Preserve an ordinary meeting's actual subjects, discussion, decisions, open questions, and assigned follow-up.
- `PRODUCT-BACKLOG@core`: Maintain an emergent, ordered inventory of possible product work and its refinement basis.
- `PRODUCT-FEEDBACK-REGISTER@core`: Maintain sourced discovery inputs and feedback through triage and routing to authoritative downstream records.
- `PRODUCT-ROADMAP@core`: Communicate evolving product direction, intended outcomes, and dependencies across planning horizons.
- `PULL-REQUEST-DESCRIPTION@core`: Present an identified change for review and integration with its rationale, validation, risks, and pending decisions.
- `REPOSITORY-OVERVIEW@core`: Provide a concise entrypoint to a development repository and its authoritative documentation.
- `RESEARCH-PARTICIPANT-INFORMATION@core`: Explain a planned study and its participation and data arrangements to prospective participants.
- `SECURITY-ADVISORY@core`: Communicate supported vulnerability applicability and recipient actions across affected and fixed product versions.
- `SERVICE-STATUS-REPORT@core`: Maintain a bounded view of observed service-period results, data coverage, trends, and follow-up decisions.
- `SUPPORT-GUIDE@core`: Direct recipients to established help, defect, improvement, and security-reporting routes.
- `TECHNICAL-COMMERCIAL-PROPOSAL@core`: Present a bounded engineering offer with scope, deliverables, estimates, price, and proposed terms.
- `TECHNICAL-DEBT-REGISTER@core`: Track known engineering compromises, their carrying effects, treatment choices, and reassessment.
- `TECHNICAL-REFERENCE@core`: Provide version-bound lookup information for technical interfaces, symbols, commands, or settings.
- `THIRD-PARTY-NOTICES@core`: Assemble sourced third-party notices and attribution accompanying an identified distributed artifact.
- `TUTORIAL@core`: Guide a learner through a bounded practice exercise with a learning objective and observable checkpoints.
- `USER-RESEARCH-FINDINGS@core`: Report supported discovery observations, interpretations, disagreements, and implications from research actually performed.
- `USER-RESEARCH-PLAN@core`: Plan exploratory research into unknown user needs, behavior, and operating contexts.
- A public `llms.txt` overview with a complete-catalog entrypoint and selected Markdown references for automated readers, following the [llms.txt format](https://llmstxt.org/).
- A released and adopted specification authoring standard in `CONTRIBUTING.md`, with structured input and output templates, exact composition rules, catalog integration, and acceptance gates.

### Changed

- Revised `SECURITY-ADVISORY@core` under authoring standard 2.0.0: admit zero or more independently sourced severity assessments by context, scheme, edition, inputs and limits, and zero or more selected native exports by schema, version, artifact, mapping, validator and check status. Preserve affected, not-affected and unknown applicability, separate fix availability, disclosure authority and history, and recipient limits. New obligations apply on selection without retrospective migration. Identity, catalog row, counts, common method and the other 142 contracts remain unchanged; synthetic checks do not establish published-schema conformance, disclosure permission, a product fix or adoption.
- Revised `TUTORIAL@core` under authoring standard 2.0.0: distinguish untested draft from supported learner-ready applicability by edition and environment; require safe complete walkthrough evidence, observable checkpoints and recovery, reflection, bounded cleanup and drift reassessment. New obligations apply on selection without retrospective migration. Identity, catalog row, counts, common method and the other 142 contracts remain unchanged; same-author synthetic execution does not establish human learning, competence, adoption or release.
- Revised `TECHNICAL-REFERENCE@core` under authoring standard 2.0.0: reconcile source inventories, indexes, definitions and explicit gaps; preserve usable item/version locators and native authority; define applicable API, CLI, settings and exposed protocol attributes; distinguish expected examples, actual checks, generation and schema claims; require bounded lookup and drift reassessment. New obligations apply on selection without retrospective migration. The identity, catalog row, counts, common method and other 142 contracts are preserved; synthetic author-self evidence does not establish product execution or human usability.
- Revised `PRODUCT-BACKLOG@core` under authoring standard 2.0.0: preserve controlling native work states and transitions, make normalized views optional with explicit mapping editions, conditions, loss, unmapped and unknown dispositions, and support independent mission-selected sizing dimensions. Selection, completion evidence, commitment and acceptance remain distinct; changed sources require reassessment.
- Revised `PULL-REQUEST-DESCRIPTION@core` under authoring standard 2.0.0: explicit standalone H1 versus host-owned title and metadata, immutable check provenance and changed-snapshot stopping, concise small-change presentation, concrete non-runtime results, actual failed/not-run checks and material rollout or irreversible reversal concerns. These two revisions apply on selection; existing finished documents and unaffected contracts are not retrospectively migrated.
- Revised `ELICITATION-INSTRUMENT@core` under authoring standard 2.0.0: edition- and context-bound draft/administration readiness, method- and risk-bound pilot or equivalent checks, justified unpiloted use, explicit nonresponse and stop routes, and renewed checks after changed inputs. No universal participant pilot obligation or retrospective migration is introduced.
- Revised `RESEARCH-PARTICIPANT-INFORMATION@core` under authoring standard 2.0.0: observable supplied-edition retrieval and understanding criteria, actual assessment status and unmet-check stopping, checked accessible equivalents, and separation of information, comprehension, and consent. The client convention, identities, catalog rows, and other 141 contracts remain unchanged; synthetic author-self checks do not establish participant comprehension or adoption.
- Released and adopted specification authoring standard 2.0.0 and both templates: mission/source discovery before classification; independent task and obligation coverage; evaluated ordinary, incomplete, and boundary finished instances; per-type frontmatter; explicit standalone/native projections; proportionate semantic roles; controlled supporting definitions and examples; deterministic rendering after design. The request interface changes for new contributions and explicitly requested revisions, effective from collection release 2026-10-06. Existing contracts and retained 1.0.0 evidence are not retrospectively migrated.
- Public overview, catalog guidance, and automated-reader discovery now reference the shared registry and the 2.0.0 applicability and evaluation rules. Catalog identities, paths, rows, counts, and all 143 existing specifications are preserved by this common-system revision.
- Revised `README.md` for human readers, with the collection's purpose, organization, usage, and documentation architecture.
- Linked the specification-maintenance standard and templates from the public overview, catalog, and automated-reader entrypoint.
- Corrected unreleased notes and entrypoint references to `AGENTS.md` and operational placeholder directories that are absent from this checkout.
- Clarified that the catalog count includes specification variants; the 120 existing specification files retain their contents.

### Removed

- Supporting research, census, evaluation records, and demonstration examples from `authoring/`. Specification maintenance retains the authoring standard and its request and specification templates.
