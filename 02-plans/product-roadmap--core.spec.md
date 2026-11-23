---
title: "Product roadmap specification"
description: >-
  Defines the authoring contract for product roadmaps communicating evolving product direction, themes, intended outcomes, dependencies, and feasibility assumptions across multiple planning horizons. Requires explicit distinction between directional forecasts and established commitments, clear horizon framing, dependency visibility, and defined revision and review triggers so product owners, engineering leads, and stakeholders align priorities without treating roadmap entries as approved requirements or contractual promises.
topics:
  - "planning"
  - "product-and-discovery"
  - "product-roadmap"
  - "product-strategy"
  - "planning-horizons"
  - "outcome-planning"
  - "forecast-vs-commitment"
  - "product-dependencies"
use_when:
  - "Product and engineering leaders need to communicate evolving product direction, themes, and intended outcomes across multiple horizons."
  - "An author is documenting strategic dependencies and feasibility assumptions while clearly separating forecasts from commitments."
  - "A reviewer is checking that a product roadmap avoids claiming unachieved outcomes or duplicating backlog execution details."
not_for:
  - "Maintaining an ordered inventory of emergent work items and refinement states, which belongs in an ordered product backlog."
  - "Detailed engineering delivery schedules or periodic progress tracking, which belong in development plans or status reports."
  - "Binding commercial offers or executed contractual delivery commitments."
---

# Product roadmap specification

## Identity and selection

- **Specification ID:** `PRODUCT-ROADMAP@core`.
- **Purpose:** Communicate evolving product direction, intended outcomes, and dependencies across planning horizons.
- **Intended readers:** Product owners, product managers, engineering leads, stakeholders, and investment decision makers.
- **Decision or action supported:** Align priorities and revisit future direction while distinguishing forecasts from established commitments.
- **Use when:** Product evolution needs communication across more than one planning horizon.
- **Scope boundaries:** Plan outcome-oriented product direction across horizons; exclude ordered work-item masters, detailed delivery execution, contractual commitments, and achieved-outcome claims.

## Authoring inputs and unresolved facts

Obtain product boundary and strategy, sourced user or business needs, goal decisions, themes and intended outcomes, planning horizons, dependencies and capacity assumptions, estimate confidence, actual commitment decisions where present, and review responsibility and cadence or triggers.

Expose unknown need, outcome measure, horizon, dependency, authority, or commitment basis with consequence and resolving action; name assigned owners only. An uncertain date remains a forecast or horizon gap. Do not invent commitments, measured value, staffing, market facts, or authorized investment.

## Finished-document contract

- **Title:** Identify the product and covered horizons and name its product roadmap.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State direction and source basis before outcome themes and horizons; follow horizons with dependencies, commitments, and review rules. Heading wording may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Product roadmap (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Product direction and basis | Required | Identify product, audience, strategic goal and decision state, source needs, as-of point, planning scope and exclusions, and the client or receiving-party element when applicable. |
| Themes, outcomes, and horizons | Required | Map each initiative or theme to a sourced problem and intended outcome, an observable outcome basis or gap, and a stated horizon. Show ordering rationale and confidence; solution features remain candidates unless actually chosen. |
| Dependencies and feasibility assumptions | Required | Identify material capacity, supplier, technical, regulatory, learning, or market dependencies only when grounded in actual inputs. State uncertainty, feasibility gaps, and conditions that would change the proposed direction. |
| Forecasts, commitments, and review | Required | Distinguish aspirational direction, forecast, and actual committed scope using their sources and decision rights. Identify review ownership, update triggers, changed or withdrawn directions, and links to real backlog or delivery plans without duplicating them. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Direction and goal | Exactly one bounded direction account in Product direction and basis. | Link goal to sourced needs and its actual proposal or endorsement state. |
| Theme or initiative | One or more in Themes, outcomes, and horizons. | Each has problem, expected outcome, observation basis or gap, and horizon; outcomes are intended rather than achieved. |
| Planning horizon | Two or more distinguishable horizons in Themes, outcomes, and horizons. | Use dates, ranges, or defined relative horizons with a common as-of basis; a horizon does not create a delivery promise. |
| Dependency or assumption | Zero or more material items in Dependencies and feasibility assumptions. | State source, effect, uncertainty, and resolving or review trigger; no feasibility guarantee is inferred. |
| Commitment status | Exactly one of direction, forecast, or committed for each initiative in Forecasts, commitments, and review. | Direction expresses intent; forecast adds a sourced estimate; committed requires an actual decision and bounded scope. Changed scope requires reassessment and a new commitment decision where applicable; record prior states rather than silently downgrading commitments. |
| Roadmap revision and review | Exactly one as-of revision and one upkeep account in Forecasts, commitments, and review. | Identify responsible role or gap and how changed needs, evidence, capacity, or commitments trigger update. |

Use outcome prose and a horizon table. A visual timeline may supplement the roadmap when uncertainty and commitment state remain visible in text. The roadmap controls direction; backlog, delivery plans, and actual agreements retain their detailed work and commitment authority.

## Quality criteria

- Direction and goals have a sourced need basis and explicit decision state.
- Every theme links problem, intended outcome, observation basis, and one defined horizon within the cross-horizon view.
- Material dependencies, capacity premises, and feasibility uncertainty are explicit and revisitable.
- Direction, forecast, and committed states have their required basis; revision and review preserve actual commitment decisions.
