---
title: "User and context research findings specification"
description: >-
  Defines the authoring contract for user and context research findings reports presenting supported discovery observations, themes, interpretations, participant disagreements, and implications derived from exploratory research actually performed. Covers research questions and round boundaries, actual methods and achieved participant coverage, source-grounded observations, transparent interpretation limits, open questions, confidence levels, and sharing constraints while excluding unperformed work, raw source masters, approved requirements, and formal solution validation.
topics:
  - "evidence"
  - "product-and-discovery"
  - "user-research-findings"
  - "discovery-evidence"
  - "qualitative-synthesis"
  - "research-implications"
  - "sample-limits"
  - "user-insights"
use_when:
  - "An exploratory user research round has collected observations or ended with capture limits that must be synthesized for decision makers."
  - "A researcher is reporting grounded themes, participant disagreements, sample limitations, and implications for needs or product work."
  - "A reviewer is checking whether discovery insights trace to real collection records and preserve confidence and scope boundaries."
not_for:
  - "Planning recruitment, methods, and ethics before conducting research, which belongs in a user research and discovery plan."
  - "Preserving unedited raw statements and session transcripts, which belongs in an elicitation and source record."
  - "Judging intended-use fitness of a delivered solution against fixed needs, which belongs in a validation evidence record."
---

# User and context research findings specification

## Identity and selection

- **Specification ID:** `USER-RESEARCH-FINDINGS@core`.
- **Purpose:** Report supported discovery observations, interpretations, disagreements, and implications from research actually performed.
- **Intended readers:** Researchers, analysts, product owners, designers, requirements stewards, and authorized stakeholder readers.
- **Decision or action supported:** Use discovery evidence to revisit needs or product work while retaining sample, context, and interpretation limits.
- **Use when:** A research round acquired observations about users or contexts, or an initiated round ended with capture limitations to report.
- **Scope boundaries:** Report exploratory discovery findings and their source basis; exclude unperformed research, formal solution fitness determinations, raw-source masters, and approved requirements.

## Authoring inputs and unresolved facts

Inspect actual research questions, round and setting, methods and instrument editions, recruitment and participant or corpus coverage, permitted source evidence, analysis operations, contrary observations, capture failures, disclosure limits, and actual downstream decisions if any.

Expose unknown selection, participation, context, method edition, observation, or analysis basis with its consequence, resolving action, and assigned owner if known. An unsupported pattern remains a hypothesis. A round without usable observations has capture limitations and unanswered questions rather than invented findings. Do not invent quotations, prevalence, causal effects, acceptance, or changed requirements.

## Finished-document contract

- **Title:** Identify the research subject and round and name the document as user and context research findings.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State questions, actual context, and method before observations; place interpretation and implications after the evidence, followed by open questions and sharing limits. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| User and context research findings (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Questions, round, and evidence boundary | Required | Identify questions, actual round and setting, decision use, as-of point, exclusions, and the client or receiving-party element when applicable. Cite the plan when used and state what actually occurred. |
| Method and participation actually used | Required | Describe actual collection, instrument editions, selection and recruitment, achieved participant or corpus coverage, accessibility and proxy limits, analysis procedure, deviations, and missing perspectives. Use minimized participant descriptions. |
| Observations and source support | Required | State supported observations with permitted source locators, context, and contradictory or exceptional observations. Identify actual counts only with units and denominators; no usable observations requires an explicit statement and capture-failure account. |
| Interpretation and implications | Required | Separate themes and interpretations from observations and analyst hypotheses. Link each interpretation to its supporting and contrary evidence; describe implications for needs, design, or possible work as recommendations unless an actual decision is cited. |
| Open questions, confidence, and sharing | Required | State unanswered questions, sampling and context limits, analysis uncertainty, further research or decisions needed, access and retention constraints, and actual review state. Do not equate repeated observations with population prevalence or declare product validation from discovery. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Research round | Exactly one round or explicitly bounded combined set in Questions, round, and evidence boundary. | Each combined round retains its actual setting and method differences. |
| Achieved coverage | Exactly one account in Method and participation actually used. | Planned recruitment is separate from actual participation; missing groups remain visible. |
| Observation | Zero or more supported observations in Observations and source support. | Each has a source locator and context; zero requires an explicit unusable-evidence or assessed-empty basis. |
| Finding or theme | Zero or more interpretations in Interpretation and implications. | Relate each to actual observations and contrary evidence; label analyst hypotheses without manufacturing agreement. |
| Implication and decision | Zero or more recommendations and actual decision citations in Interpretation and implications. | Proposed need or backlog changes do not become approved work by being mentioned. |
| Confidence and disclosure limit | Exactly one account in Open questions, confidence, and sharing. | Match confidence to selection, context, and analysis actually used; disclose only authorized, minimized evidence. |

Use a compact GFM summary or evidence-to-finding table sized to the round. A long academic report is not required. Keep restricted recordings and raw notes in their actual source location, and distinguish analyst synthesis from participant wording. The findings report controls interpretation; source records control acquisition.

## Quality criteria

- Questions, actual round, method, and achieved coverage match the evidence inspected and preserve missing perspectives.
- Observations and contrary cases have permitted source locators; counts are bounded and missing evidence stays visible.
- Themes and implications trace to evidence, with hypotheses, recommendations, and actual decisions distinguishable.
- Confidence, unanswered questions, review state, and permitted sharing remain within the achieved sample and actual method.
