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
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State direction and source basis before outcome themes and horizons; follow horizons with dependencies, commitments, and review rules. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Product direction and basis | Required | Identify product, audience, strategic goal and decision state, source needs, as-of point, planning scope and exclusions, and client or receiving-party element. |
| Themes, outcomes, and horizons | Required | Map each initiative or theme to a sourced problem and intended outcome, an observable outcome basis or gap, and a stated horizon. Show ordering rationale and confidence; solution features remain candidates unless actually chosen. |
| Dependencies and feasibility assumptions | Required | Identify material capacity, supplier, technical, regulatory, learning, or market dependencies only when grounded in actual inputs. State uncertainty, feasibility gaps, and conditions that would change the proposed direction. |
| Forecasts, commitments, and review | Required | Distinguish aspirational direction, forecast, and actual committed scope using their sources and decision rights. Identify review ownership, update triggers, changed or withdrawn directions, and links to real backlog or delivery plans without duplicating them. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
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
