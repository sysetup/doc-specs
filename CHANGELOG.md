# Changelog

Notable changes to this collection are recorded here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Changes awaiting release are grouped under `Unreleased`.
Collection releases are identified by date; the authoring standard has its own version.

## Unreleased

### Changed

- Updated `README.md` to describe the actual repository contents, link automated-reader and license resources, and remove the obsolete three-tree installation convention and dedicated operational proposal-directory workflow.
- Aligned `llms.txt` with the repository's documentation scope and ownership of finished documents and operational instructions.
- Corrected the editorial reference in authoring standard 2.0.0 to removed `A01–A23` supporting material. Authoring rules, request and template interfaces, specification contracts, catalog identities, and counts are unchanged.

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
