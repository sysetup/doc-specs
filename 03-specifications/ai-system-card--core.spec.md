---
title: "AI model or system card specification"
description: >-
  Defines the authoring contract for AI model and system cards disclosing the identity, maturity, ownership, intended uses, out-of-scope or prohibited boundaries, architecture or compound-system composition, runtime safeguards, training and grounding data provenance, documented capabilities, limitations, known biases, cited empirical evaluation results, human-oversight obligations, operational monitoring constraints, and conditional machine-readable registry exports for an AI model or compound AI system. Keeps disclosed claims strictly grounded in cited dataset and evaluation records without fabricating undocumented upstream data or deployment authorization.
topics:
  - "specifications"
  - "ai-and-ml"
  - "risk-and-safety"
  - "ai-system-card"
  - "model-card"
  - "intended-use"
  - "ai-transparency"
  - "human-oversight"
use_when:
  - "An AI model or compound AI system requires structured transparency documentation for integrators, deployers, operators, or governance reviewers."
  - "A model or system owner is disclosing intended and out-of-scope uses, system composition, data provenance summaries, known biases, and human-oversight bounds."
  - "A reviewer is verifying that AI capability and safety disclosures cite real evaluation evidence and expose undisclosed upstream provenance honestly."
not_for:
  - "Preserving detailed empirical benchmark runs, scoring harnesses, stochastic variance, and red-team findings, which belongs in an AI evaluation report."
  - "Documenting a single dataset's full schema, collection methodology, annotation rules, and licensing in depth, which belongs in a dataset specification."
  - "Providing step-by-step installation and everyday end-user operating procedures for general software, which belongs in a product guide."
  - "Conducting an internal personal-data legal necessity and privacy risk assessment, which belongs in a data protection impact assessment."
---

# AI model or system card specification

## Identity and selection

- **Specification ID:** `AI-SYSTEM-CARD@core`.
- **Purpose:** Define a transparent, version-bound disclosure card for an AI model or compound AI system covering its identity, intended and out-of-scope uses, composition, data provenance summary, cited evaluation results, known limitations, human-oversight requirements, and operational boundaries.
- **Intended readers:** Integrators, deployers, application developers, operators, safety and compliance reviewers, affected-user representatives, and model or system maintainers.
- **Decision or action supported:** Judge whether the AI model or system fits a proposed deployment context, configure required safeguards and human oversight, locate authoritative evaluation and dataset records, and avoid unsupported or prohibited use.
- **Use when:** A standalone machine-learning model, foundation model, fine-tuned checkpoint, or compound AI system (combining models, prompts, retrieval, tools, or guardrails) requires structured disclosure of capabilities, boundaries, provenance, and operational constraints.
- **Scope boundaries:** Disclose subject-level identity, intended uses, architecture or system composition, provenance summaries, cited evaluation outcomes, risks, and operational bounds for one AI model or system version; exclude primary empirical benchmark logs, full dataset specifications, legal compliance certifications, and unverified marketing claims.

## Authoring inputs and unresolved facts

Obtain the AI model or system identity, exact version or checkpoint identifier, release or maturity state, subject scope (standalone model versus compound AI system), modalities, architecture summary, accountable developer or maintainer role, license or access terms, and intended update cadence; primary intended uses, target users, operating assumptions, and out-of-scope or prohibited uses; for compound systems, every constituent model revision, orchestration or prompt layer, retrieval corpus, tool integration, and runtime guardrail; training, fine-tuning, alignment, grounding, and evaluation data provenance summaries with citations to dataset specifications when they exist; actual AI evaluation reports, red-team records, threat models, or privacy assessments with their exact assessed configurations and editions; known failure modes, biases, subgroup disparities, hardware or runtime constraints, human-oversight requirements, user-disclosure duties, monitoring and drift triggers, and feedback or incident reporting routes; and for any selected machine-readable registry or card export, its schema, version, artifact locator, mapping, validator, and check status.

Expose unknown upstream training data, undisclosed third-party weights provenance, unperformed evaluations, unverified safeguards, missing oversight owners, or unrun export checks with their consequence for safe deployment, resolving action, and actual owner only when assigned. Do not infer upstream dataset contents when a third-party provider does not disclose them. Do not present planned evaluations, proposed guardrails, or upstream base-model scores as observed performance of a fine-tuned or compound system. Missing evaluation evidence or unresolved high-risk boundaries block presenting the card as supporting unrestricted production deployment.

## Finished-document contract

- **Title:** Name the AI model or system and its covered version or release and identify the document as its model card or system card matching its declared subject scope.
- **Frontmatter:** Required on standalone GFM documents; omitted on selected machine-readable native model-registry or card-schema exports whose hosts or formats manage metadata natively. Begin standalone GFM documents with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), excluding internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values, followed by the H1 title. Subject identity, version, maturity, evaluation citations, and export check status belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract and this type's projection policy.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish subject identity, scope, and intended uses before composition and data provenance; place capabilities, limitations, and cited evaluations before risks, oversight, operational constraints, and any native export binding. Heading wording may vary.
- **Presentation:** Scale sections, summary tables, and component inventories to a standalone model or a multi-component AI system without adding empty chapters for inapplicable orchestration layers. Required roles may share sections while keeping version bindings, out-of-scope boundaries, evaluation citations, and undisclosed gaps immediately retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| AI model or system card (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one subject-specific H1 naming the AI model or system and covered version. Maturity, composition, provenance, cited evaluations, and corpus-level governance inheritance where applicable remain body content. | Use GFM prose, component tables, and structured citation summaries bound to inspected model versions, dataset specifications, and evaluation reports. Cited evidence records remain authoritative for full methodology and raw metrics; model, prompt, guardrail, or data updates require card reassessment before retaining current applicability. |
| Selected registry or card export (native) | A machine-readable model-registry card or native schema export omits Semantic-Discovery YAML frontmatter and owns its format-native fields without adding a duplicate H1. Missing native schema fields remain explicitly omitted rather than guessed from prose. | Each declared native schema and version controls its own field syntax and validation rules. Validator status applies only to the checked artifact, schema version, and mapping; GFM prose does not establish native schema validity, and changes to either surface require re-verification. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity, maturity, and ownership | Required | Identify the AI model or system, declare whether the subject is a standalone model or compound AI system, state exact version or checkpoint identity, release date or as-of point, maturity state (`experimental`, `preview`, `production`, `deprecated`, or `retired`), input and output modalities, architecture summary, accountable developer or maintainer role, licensing or access terms, and the client or receiving-party element when applicable. |
| Intended uses and out-of-scope boundaries | Required | State primary intended tasks, target user or integrator roles, supported languages or domains, and required operating assumptions. Explicitly enumerate out-of-scope, unsupported, high-stakes, or prohibited uses and downstream adaptation boundaries (such as fine-tuning, distillation, or autonomous action limits). |
| System composition and runtime safeguards | Conditional when the subject composes multiple models, retrieval sources, external tools, orchestration logic, or runtime safeguards beyond a standalone model | Enumerate each constituent model and exact version, prompt or workflow orchestration layer, retrieval or memory source, external tool or action permission boundary, input and output filters or guardrails, and fallback or abstention behavior. State explicitly when a standalone model card omits this role in Identity, maturity, and ownership. |
| Data provenance and training or grounding basis | Required | Summarize training, fine-tuning, preference-alignment, grounding, and evaluation data origins, modalities, temporal cutoffs, filtering or deduplication principles, and privacy or rights status. Cite authoritative dataset specifications by identity and edition where they exist; explicitly mark undisclosed third-party upstream training data as undisclosed rather than assuming compliance or coverage. |
| Capabilities, limitations, and evaluation summary | Required | Summarize demonstrated capabilities, known technical failure modes, subgroup or domain disparities, calibration or hallucination limits, and environmental sensitivities grounded strictly in cited actual evaluation records. For each cited result, state the evaluated configuration, suite edition, date, and locator, and distinguish base-model observations from system-level evaluations. Mark unevaluated areas explicitly. |
| Risks, oversight, and operational constraints | Required | State material safety, security, privacy, fairness, and misuse risks with citations to controlling threat models or data protection impact assessments when they exist. Specify required human-oversight controls, user transparency or AI-interaction disclosures, runtime monitoring and drift reassessment triggers, compute or latency prerequisites, incident and feedback reporting channels, and lifecycle deprecation or update rules. |
| Native registry or card export binding | Conditional when one or more machine-readable model-registry or card-schema exports are selected | For each selected export, state the schema and version, controlling artifact locator, human-to-native field mapping, generation inputs, validator, and actual check status (`pass`, `fail`, `inconclusive`, or `not-run`). Preserve unmapped or missing fields explicitly and require re-checking after any change to the card or export schema. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| AI subject identity | Exactly one bounded standalone model or compound AI system and its exact version in Identity, maturity, and ownership. | Bind the entire card to one version or explicitly bounded release line; distinguish base weights from fine-tuned checkpoints or wrapped systems. |
| Use boundary | One or more intended uses and one or more out-of-scope or prohibited uses in Intended uses and out-of-scope boundaries. | Separate supported operational conditions from unsupported or prohibited contexts; silence does not permit high-risk deployment. |
| Compound component | One per constituent model, retrieval store, tool, orchestrator, or guardrail when the subject is a compound AI system in System composition and runtime safeguards. | State role, exact version or edition, authority boundary, and failure or fallback behavior; omit only when the subject is explicitly declared a standalone model. |
| Data provenance summary | One structured account per applicable data stage (pretraining, fine-tuning, alignment, grounding, evaluation) in Data provenance and training or grounding basis. | Cite authoritative dataset specifications where present; record undisclosed upstream provider data as undisclosed rather than guessing contents or rights. |
| Evaluation citation | Zero or more citations to actual evaluation reports in Capabilities, limitations, and evaluation summary. | Identify report locator, assessed configuration, suite edition, date, key observed scope, and limits. If no empirical evaluation has been performed on the exact configuration, state that gap explicitly. |
| Limitation and bias account | One or more known technical, domain, linguistic, or fairness limitations in Capabilities, limitations, and evaluation summary. | Tie each stated limitation to observed evidence or explicit architectural bounds; distinguish assessed absence of a failure mode from unexamined scope. |
| Oversight and operational constraint | One coherent operating-control account in Risks, oversight, and operational constraints. | Define required human review, user disclosure, runtime monitoring, fallback triggers, and escalation channels without assuming downstream deployers will infer them. |
| Lifecycle and reassessment trigger | One maintenance and change account in Identity, maturity, and ownership and Risks, oversight, and operational constraints. | Name concrete changes (weights retrain, prompt or guardrail edits, tool additions, drift, incidents) that invalidate prior disclosures and require a new card revision. |
| Native card export | Zero or more selected machine-readable export bindings in Native registry or card export binding. | Each entry binds schema, version, artifact locator, mapping, validator, and its own check status; checks do not transfer across formats or revisions. |

Use concise disclosure prose, a structured metadata summary table for subject identity and versions, a component table for compound AI systems, and an evaluation citation table linking exact assessed configurations to their authoritative reports. Keep detailed benchmark methodology in AI evaluation reports and full dataset provenance in dataset specifications rather than duplicating them into the card. Do not insert blank rows, invented metrics, unverified safety guarantees, or placeholder contact routes.

## Quality criteria

- The card binds unambiguously to one AI model or compound AI system version, clearly declares standalone versus compound scope, and states its maturity, ownership, and terms.
- Intended uses, operating assumptions, and out-of-scope or prohibited uses are explicit enough for a deployer to determine fit without guessing.
- Compound AI systems enumerate every material constituent model, retrieval source, tool permission, and runtime safeguard; standalone model cards state their single-model boundary explicitly.
- Data provenance summaries cite actual dataset specifications where available and expose undisclosed upstream third-party training data honestly.
- Every capability, bias, or safety claim traces to a cited empirical evaluation of the matching configuration, keeping base-model scores, system-level scores, and unevaluated scope distinct.
- Human-oversight obligations, user disclosures, runtime drift triggers, feedback channels, and lifecycle reassessment conditions are concrete and actionable.
- Any selected machine-readable registry or card export declares its schema, version, artifact locator, mapping, validator, and actual check status without treating GFM prose as schema validation.
