# Technical debt register specification

## Identity and selection

- **Specification ID:** `TECHNICAL-DEBT-REGISTER@core`.
- **Purpose:** Track known engineering compromises, their carrying effects, treatment choices, and reassessment.
- **Intended readers:** Architects, developers, maintainers, product owners, and engineering investment decision makers.
- **Decision or action supported:** Prioritize or defer treatment of known maintainability compromises using sourced consequences and explicit decision state.
- **Use when:** A known compromise creates continuing engineering cost or constraints without necessarily constituting a defect.
- **Scope boundaries:** Maintain observed technical compromises and treatment disposition; exclude uncertain future-event risk, defect closure, and unsupported financial valuation or productivity inference.

## Authoring inputs and unresolved facts

Inspect the product or engineering boundary, concrete compromise and locations, actual observation and versions, engineering consequences or evidence gaps, origin when known, treatment options and dependencies, priority and estimation basis, actual ownership and deferral decisions, completion checks, and revisit triggers.

Expose unknown location, effect, cause, effort estimate, owner, or disposition with consequences and resolving action. Do not invent a nonconformance, cause, monetary cost, return on investment, or accepted risk. Unverified treatment stays unverified and missing ownership remains an assignment gap.

## Finished-document contract

- **Title:** Identify the engineering scope and name its technical debt register.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope and evaluation rules before debt entries; follow consequences with treatment, disposition, and upkeep. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and assessment rules | Required | Identify boundary, as-of point, steward and decision rights or gaps, prioritization vocabulary and basis, master records, exclusions, and client or receiving-party element. |
| Known compromise entries | Required | Record each compromise's stable key, concrete location and version, observation source, context, and rationale or unknown origin. State assessed-empty scope explicitly; a general suspicion without a known compromise remains a research or risk question. |
| Carrying effects and treatment options | Required | State observed maintenance cost, complexity, coupling, support limits, or other consequences with evidence and units where used. Separate estimates from measured effects. Identify treatment alternatives, dependencies, effort basis, and real related defect or risk records. |
| Disposition and reassessment | Required | Record owner or gap, priority rationale, proposed or selected treatment, deferral basis and revisit trigger, actual implementation and checking when present, and current state. Preserve superseded entries and failed treatments; closure does not prove unrelated risks or defects are closed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Debt item | Zero or more known compromises in Known compromise entries. | Each has one immutable identity, location, version, and observation source; no requirement breach is assumed. |
| Carrying effect | One or more effects or an explicit effect gap per item in Carrying effects and treatment options. | Qualitative engineering constraints are permitted; numbers require a source, period, unit, and estimate or observation label. |
| Treatment option | Zero or more in Carrying effects and treatment options. | State alternative, dependencies, effort or uncertainty, and expected effect; an expected benefit is not achieved value. |
| Disposition state | Exactly one of identified, assessed, selected, deferred, treated, checked, or retired per item in Disposition and reassessment. | Identified may become assessed after effects and options are examined; assessed may become selected or deferred with decision basis. Selected may become treated only after actual implementation; treated may become checked only after assessment of the intended effect. Any resumed analysis returns to assessed with history. Retired requires the compromise's context to be removed or superseded with basis; deferral and checking do not imply risk acceptance. |
| Owner and revisit | One assignment or gap and one revisit condition per item in Disposition and reassessment. | Deferral names the actual deciding role and trigger; no assigned owner is invented. |
| Treatment evidence | Zero or more actual implementation and effect-check records in Disposition and reassessment. | Separate treatment applied from its demonstrated effect; a failed check remains visible and cannot support a favorable treated-effect claim. |

Use an item table and short consequence or option notes. Link to locations, decisions, backlog items, and actual treatment evidence without duplicating their masters. The register controls compromise disposition; defects and risks retain separate applicability, authority, and closure.

## Quality criteria

- Scope, current source basis, ownership, and priority rules identify the maintained compromise population.
- Each item is a sourced known compromise with a stable key and location, rather than a guessed defect or future risk.
- Carrying effects and options preserve source, units, estimates, alternatives, and uncertainty.
- States, deferral, revisit conditions, and treatment claims match actual decisions and retained implementation or checking evidence.
