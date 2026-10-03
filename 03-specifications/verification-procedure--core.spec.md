# Verification procedure specification

## Identity and selection

- **Specification ID:** `VERIFICATION-PROCEDURE@core`.
- **Purpose:** Define a repeatable method and decision criteria for assessing whether a bounded item conforms to identified technical requirements or specifications.
- **Intended readers:** Verification engineers and operators, requirement owners, technical reviewers, and people deciding how conformance evidence will be assessed.
- **Decision or action supported:** Select and prepare an appropriate inspection, analysis, test, or demonstration; perform it repeatably; and determine what observations could support or limit a conformance conclusion.
- **Use when:** A specific technical obligation or coherent set of obligations needs a planned, executable conformance assessment method.
- **Scope boundaries:** Define the assessment method for the stated item and technical obligations, with an explicit obligation-to-criterion mapping and the conditions and evidence needed to support a conformance judgment.

## Authoring inputs and unresolved facts

Obtain the established project technical requirements or specification clauses and their editions, item and configuration to be assessed, selected verification method, rationale for that method, required conditions and sample basis, expected outcomes or conformance limits, measurement or analysis capability, safety and execution constraints, evidence needs, and review or decision authority if the project defines one. Read each supplied requirement's wording and identify the item and conditions to which it applies; do not derive a criterion from a title alone. State the requirements, method, and concrete criteria at the detail needed for assessment, with their project origins, editions, and locators.

If a requirement, configuration, criterion, method capability, sample basis, or evidence rule is unknown or undecided, identify the affected obligation, consequence for a conformance judgment, resolving action, and actual owner if assigned. Mark the affected method unready for conclusive use until a material gap is resolved. If the requirement itself is ambiguous or untestable, escalate its clarification rather than manufacture a threshold. Do not report a planned inspection, calculation, test, or demonstration as executed or invent observations, conformance decisions, approvals, or authorizations.

## Finished-document contract

- **Title:** Identify the bounded item or verification scope and name the document as its verification procedure; distinguish the method or procedure edition when results will cite it.
- **Frontmatter:** None. Begin with the GFM title. Technical basis, configuration, and decision rules belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State subject and method before criteria; place prerequisites before steps and evidence and disposition after the actions that produce them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Verification subject and basis | Required | Identify the item, applicable configuration or selection rule, one or more established project technical requirements or clauses and their editions and locators, material exclusions, and the scope of the conformance claim this method could support. |
| Method and criterion mapping | Required | Select inspection, analysis, test, demonstration, or a justified combination; explain suitability and map each applicable requirement to observable or calculable criteria, limits, units, tolerances, uncertainty treatment, and sample or coverage rule where needed. State what an actual assessment would have to observe to treat the criterion as met, missed, or not supportable. A failed prerequisite or a stop before the assessment leaves the criterion unassessed. |
| Preconditions and capability | Required | Define required item state, environment, inputs, tools or models, personnel capability, access and safety controls, instrument calibration or model validity when relevant, and checks before assessment begins. Identify actual authorization requirements without treating this procedure as authorization. |
| Ordered assessment method | Required | Give one or more stable locally identified steps with action or examination, target or sample, required observation or calculation, expected criterion, planned evidence, and failure or invalid-condition branch. Include setup and restoration where they affect validity or safety. Identify the edition and step locators of any project-controlled execution sequence used, with its entry, capture, and return conditions. Map each action and its evidence to the technical obligation and criterion assessed. |
| Evidence, review, and disposition rules | Required | State how raw observations, model inputs, calculations, configuration, deviations, anomalies, and repeated attempts will be bound to each criterion and retained. Define review or independent check where the project requires it, and the investigation or disposition route when a criterion is missed or the comparison is not supportable. Identify the conformance decision maker and basis when assigned; bind any actual decision to the assessed configuration, observations, and criterion comparison. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Technical obligation | One or more applicable requirements or specification clauses. | State the supplied project obligation, exact origin, edition, and locator, and identify the assessed part of a compound obligation. Give its concrete criterion in the mapping rather than only a reference. |
| Item and configuration | One bounded item or coherent set with an applicable baseline, build, sample, or selection rule. | State what will actually be assessed and the rule for choosing representative samples if all units cannot be examined. A planned configuration, including a test-environment target or readiness assessment, is not evidence of the configuration actually assessed. |
| Verification method | One or more selected modes: inspection, analysis, test, or demonstration, as suitable to the obligation. | State the method, why it can expose conformance, and what it cannot establish. Identify the edition and locator of a project-controlled method record when used. |
| Criterion mapping | At least one assessable criterion per covered obligation; several obligations may share a step only when each criterion remains visible. | Define expected value or condition and comparison rule. Include units, bounds, tolerance, uncertainty, sample size, or coverage only where they affect the judgment; do not invent numeric thresholds. |
| Tool, model, or measurement basis | Conditional: include each capability whose edition, calibration, assumptions, or precision can change the result. | Give tool or model edition, input assumptions, accuracy or calibration basis, and limits as applicable. An analysis output is only as interpretable as its model and input basis. |
| Assessment step | One or more ordered steps, each with a stable local label. | State target, action, expected check, observation or calculation to capture, and branch for failed prerequisites or invalid results. A step label need not be globally unique. Timeouts apply to waits or time-sensitive criteria, not to every step. |
| Evidence and result rule | One coherent planned rule for mapping each criterion to actual observations. | Define what each assessment must capture, including item/configuration, requirement and procedure edition, actor or tool, actual values, units, raw locators, deviations, and result comparison. A missed criterion or unsupportable comparison needs an investigation or disposition route. A retest remains a distinct attempt linked to the earlier attempt. Label expected values as planned. Define how an actual attempt's state and evidence determine `pass`, `fail`, `inconclusive`, or `not-run`; leave the outcome unassigned in the planned procedure. |

Use a requirement-to-method-to-criterion table when several obligations are covered, with columns that expose project obligation and origin, criterion, method, step, and planned evidence. Use numbered actions or a flow for the execution path and prose for method rationale and limitations. A calculation or sampling rule MAY be expressed with equations or diagrams when all inputs and assumptions are defined. Do not add empty mapping rows or prefill planned values as actual observations.

## Quality criteria

- Each covered technical obligation has an inspected source, applicable configuration, chosen method, assessable criterion, and planned evidence path; uncovered obligations are explicit.
- The method's physical or analytical capability and sample basis can support the stated conformance scope, with limitations visible.
- Criteria, steps, tools, and evidence rules agree; an operator can identify invalid conditions and avoid a later false conclusion that the criterion was met.
- The scope of each planned conformance conclusion agrees with the stated obligation, assessed configuration, method capability, and criterion; unsupported conditions remain visible.
