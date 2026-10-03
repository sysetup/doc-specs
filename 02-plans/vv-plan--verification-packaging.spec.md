# Verification plan specification

## Identity and selection

- **Specification ID:** `VV-PLAN@verification-packaging`.
- **Purpose:** Plan how a bounded item will be assessed for conformity to specified technical requirements, with traceable methods, criteria, and expected evidence.
- **Intended readers:** Verification leads and performers, requirement owners, technical reviewers, assurance roles, and recipients of a verification evidence package.
- **Decision or action supported:** Agree the conformance basis, coverage, resources, readiness, evidence package, and review route before verification work begins.
- **Use when:** A project needs a plan for assessing conformity to specified technical requirements.
- **Scope boundaries:** Specify planned technical-conformance assessment activities, resources, criteria, and evidence routes for the bounded item and its in-scope obligations.

## Authoring inputs and unresolved facts

Obtain the real subject and configuration boundary, in-scope project technical requirements or clauses with editions and status, the project need, allocation, or decision establishing each obligation and its scope, risk priorities, selected verification levels and methods, measurable criteria and their project requirement or decision basis, facilities, tools and calibration needs, schedule, dependencies, roles, whether independence is required by an established project decision or justified by risk, anomaly and evidence rules, and actual planned recipient or certification products and handoffs. Read the supplied requirement wording rather than inferring it from an ID. Existing project procedures, matrices, or lifecycle records may supply method, coverage, or sequencing data.

For an unknown requirement, configuration, method capability, criterion, independence basis, or decision right, state the gap, impact on coverage or readiness, resolution action, and actual owner if assigned. Mark an undecided choice as not established and a genuinely irrelevant level or deliverable as inapplicable with a reason. State independence as required, with the established project decision or justified risk and the role separation; as not required, because neither applies; or as not established, when that basis is unknown. Do not invent a threshold, completed test, approval, certification, independent role, or result. A plan with an unresolved conformance basis or essential criteria cannot claim that verification work is ready to start.

## Finished-document contract

- **Title:** Identify the item or effort and name the document as its verification plan.
- **Frontmatter:** None. Begin with the GFM title. The technical basis and coverage rules belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State subject and requirements before method and coverage; place resources and readiness before evidence and review. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, scope, and technical basis | Required | Identify the item, lifecycle and project boundary, configuration or selection rule, in-scope project technical requirements with origins, editions and locators, objectives, material exclusions, and project scope decisions. State the technical properties to be assessed, any unresolved requirement conflicts, and an established project decision resolving precedence when one exists. |
| Verification levels and strategy | Required | Select end-item, subsystem, integrated-system, or other levels that actually apply, with rationale and interfaces or off-nominal conditions that affect obligations. Choose suitable methods for each obligation whose method is established, and explain risk priorities and sampling or analysis limits. State the independence conclusion: required, with the established project decision or justified risk and the role separation; not required, because neither applies; or not established, when that basis is unknown. Do not invent an independent role. Program-level coordination is conditional on real scope. |
| Requirement verification mapping | Required | For each in-scope obligation or assessable facet, connect its source to method, level, target configuration, criterion, planned event or procedure, responsible role, and expected evidence when those facts are established. Show an uncovered, deferred, or excluded obligation and the basis for that treatment. Do not invent a missing element, and do not enter a result. |
| Execution resources and readiness | Required | Define schedule and dependencies, articles, facilities, environment, data, tools or models and calibration when material, role assignments, and observable entry, suspension, resumption, and exit rules with decision authority. State how a requirement or baseline change triggers replanning. |
| Evidence packaging, anomalies, and review | Required | Define capture and review rules retaining configuration, requirement and method editions, observations, criterion comparison, evidence locator, deviations, and reviewer. Define event and attempt states for planned reporting: `not-run` applies only to an activity selected for a bounded event that received no assessment action; unselected planned work has no attempt state. An attempted assessment can receive `pass`, `fail`, or `inconclusive`. A missing observation or an invalidating condition on an attempt requires `inconclusive`; do not classify it as `not-run` or introduce a separate invalid result. Preserve each retest as a distinct later attempt linked to the earlier result. Define how conformance coverage, findings, and unresolved items will reach the assigned project disposition role. |
| Certification product interface | Conditional: an established project delivery obligation supports certification or evidence handoff | State expected verification products, contents, recipient, decision role, and explicit product and handoff criteria. |
| Terms and acronyms | Conditional: terminology could change interpretation | Define project-specific terms inline or in a short section; no empty glossary or mandatory appendix. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Verification subject | One bounded item or set of items and the configuration-selection rule for assessments. | Actual events must later record the configuration used; a proposed baseline is not an as-tested fact. |
| Technical obligation | One or more in-scope, separately assessable project requirements or requirement clauses when their wording is established; otherwise one explicit source gap. | Give the supplied project requirement record, edition, and locator; preserve unresolved or proposed status. An identifier whose wording was not inspected is a gap, not an obligation. Split compound obligations where their criteria or methods differ. |
| Verification coverage mapping | One visible account per in-scope obligation or separately assessable facet. | Show requirement, method, level, criterion, configuration, planned event, role, and expected evidence when established. An in-scope obligation that lacks one of those stays an explicit gap, deferral, or exclusion with its coverage consequence. Do not invent the missing element or claim coverage from an identifier alone. A planned row has no result. |
| Verification method | One or more justified modes, such as inspection, analysis, test, or demonstration, for each obligation whose method is established. | Explain why the method can expose the required property and any limits. A named method is not an executed result. An obligation without an established method stays a gap. |
| Conformance criterion | One observable comparison rule for each obligation whose criterion is established; none while that criterion remains a gap. | Include values, units, conditions, tolerances, sampling, or uncertainty when they affect judgment. Use only established thresholds. |
| Planned evidence | One defined capture route for each assessment that is actually planned; none for a gap. | Specify observation capture with requirement, subject and configuration, method or procedure edition, criterion, evidence locator, and review. Define retention of failed attempts and distinct linked retests. |
| Exclusion or deviation | Zero or more material scope exceptions or method departures. | State reason, coverage consequence, and actual disposition authority where a binding obligation is affected. |

Use a requirement-to-method-to-criterion table for multiple obligations, with columns that expose configuration, event, responsibility, and planned evidence. For a very small scope, explicit mapped items may serve the same purpose. An existing controlled project requirement verification matrix may be cited by edition and locator with a coverage summary; if none exists, include the mapping in this plan. A schedule or flow may show sequencing and holds. Keep mapping rows at planning depth, with method descriptions and expected evidence fields rather than blank result fields or copied execution steps.

## Quality criteria

- Every established technical obligation has an inspected source. An identifier whose wording was not inspected stays a source gap. An obligation with an established path also has a suitable method, criterion, configuration rule, responsible role, and evidence path. A gap or exclusion stays explicit.
- Method capability, environment, sampling, and tool limits support only the stated conformance scope.
- The independence conclusion is required, not required, or not established. Silence is not a decision that independence is unnecessary.
- Resources and gates agree with the sequence. This plan assigns no `pass`, `fail`, `inconclusive`, or `not-run`. A later record must not count an invalidating condition, an inconclusive attempt, a gap, or a `not-run` entry as a pass.
- Any shared assessment event retains the requirement, criterion, configuration, and evidence link for each planned conformance judgment.
- Planned certification, document approval, and receiving-party decisions have explicit roles and gates; the plan does not claim completed assessments or decisions.
