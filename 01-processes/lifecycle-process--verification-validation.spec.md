# Verification and validation lifecycle process specification

## Identity and selection

- **Specification ID:** `LIFECYCLE-PROCESS@verification-validation`.
- **Purpose:** Define the reusable process for planning, performing, controlling, and reporting verification and validation while keeping their different assessment questions explicit.
- **Intended readers:** V&V leads and performers, requirements and stakeholder representatives, assurance roles, technical authorities, and recipients of assessment results.
- **Decision or action supported:** A team can select the right assessment basis and method, protect evidence and independence where needed, and apply anomaly and reporting rules without conflating conformity with fitness for use.
- **Use when:** A recurring cross-project or lifecycle V&V process needs common roles, methods, evidence rules, traceability, and reporting.
- **Scope boundaries:** Define recurring assessment paths, basis and method selection, independence, evidence controls, result-classification rules, and anomaly and reporting routes across the covered lifecycle.

## Authoring inputs and unresolved facts

Obtain the supplied project decisions establishing the V&V mandate and scope, technical obligations and stakeholder needs used as distinct assessment bases, process owner and decision rights, method-selection rules, explicit independence requirements and their project basis, configuration and environment controls, traceability and evidence systems, anomaly and retest routes, reporting recipients, and real tailoring authority. Identify the supplied project decision or justified risk that requires independence, sampling, or a particular method, and state the resulting requirement explicitly.

For an unknown or unestablished rule, identify the gap, consequence, resolving action, and owner if assigned. State the independence rule as required, not required, or not established. Do not treat an unknown mandate as a decision that independence is unnecessary. Explain when a method, independence arrangement, or assessment branch is outside the stated scope; do not turn an omitted branch into a passed result. If the assessment basis, result decision authority, or evidence-control route is missing, mark the affected process path unsuitable for authoritative conclusions. Never invent completed checks, observations, reviewer independence, approval, acceptance, or a result.

## Finished-document contract

- **Title:** Name the verification and validation lifecycle process and its organizational or product scope.
- **Frontmatter:** None. Begin with the GFM title; process edition and applicability belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State basis and authority before methods; describe performance and evidence before result reporting and feedback. Headings may use local wording.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, scope, and responsibility | Required | Define covered lifecycle stages and subjects, process owner, the project decisions establishing the V&V mandate and assessment constraints, truthful process edition or state when controlled, assessment and disposition authorities, participants, and interfaces with requirements, systems engineering, test, and acceptance. State the two distinct questions: technical conformance for verification and intended-use fitness for validation. |
| Planning and assessment design | Required | Describe intake of the correct basis, scope and coverage decisions, method and explicit criterion selection, required resources and configuration, sequencing, independence assessment, and review of readiness. Give separate routes for requirement-based verification and need- or use-based validation. Common logistics may be shared; a shared event retains two distinct conclusions. |
| Execution, traceability, and evidence | Required | Define how a later record identifies the subject and configuration, which method edition applies, what observations and limits it captures, how each basis stays linked to its method and later result, and how evidence provenance, integrity, retention, and review are controlled. Distinguish planned evidence from actual observations. |
| Anomalies and result reporting | Required | Define the classification rules a later assessment uses, plus defect or concern capture, impact assessment, disposition and re-assessment triggers. Reports keep verification coverage and conclusions separate from validation scenarios and conclusions. A planned or proposed assessment has no result. Use `not-run` only for an activity or scenario selected for a bounded event that received no assessment action; unselected planned work has no result. Classify an attempted assessment as `pass` when adequate observations establish that its criteria are met, `fail` when observations establish that a criterion is not met, or `inconclusive` when the available observations do not support a conclusion. A missing observation or an invalidating condition on an attempt is `inconclusive`, not `not-run` and not a separate invalid result. A retest is a distinct later attempt and does not erase the earlier result. Identify who may make each disposition. |
| Process assurance and tailoring | Required | Define how competence, required independence, method adequacy, evidence quality, and process effectiveness are checked; how deviations or process changes are authorized; and how lessons feed future work without rewriting actual outcomes. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Verification path | One process path for evaluating specified technical requirements or specifications. | Define the rule that links each selected obligation to a method, criterion, subject or configuration, and the evidence and disposition a later assessment must record. A favorable fitness observation does not establish technical conformance. |
| Validation path | One distinct path for evaluating stakeholder needs or intended use in representative conditions. | Define the rule that links each need or use scenario to evaluation criteria, context, fidelity limits, and the observations and fitness conclusion a later assessment must record. A conforming technical test alone does not establish fitness for use. |
| Method rule | One or more rules for selecting and controlling inspection, analysis, test, demonstration, or other suitable methods. | State method suitability, limits, calibration or qualification when material, and the observations and conditions required to support a usable result. |
| Independence rule | One rule for deciding whether organizational or technical independence is required for each applicable activity class. | Require it only for an established project decision or justified risk, and then state the role separation. When neither applies, the rule says independence is not required. When that basis is unknown, the rule says the decision is not established. Do not force universal independence, invent an independent role, or treat different job titles as independence. |
| Trace link | One route connecting basis, planned assessment, actual subject or configuration, evidence, anomaly, and disposition. | Keep requirement-verification coverage separate from stakeholder or intended-use validation coverage. A shared event or register may store both only when each path keeps its own basis, criterion, evidence, and conclusion. |
| Evidence and result | One rule for what a later record must capture. | Require provenance, configuration, timing, criteria, observations, limitations, and reviewer for an attempted assessment. Its evidence must support `pass`, `fail`, or `inconclusive` under the rules in the anomaly section. Bind each result to its attempt; retain the earlier attempt and result when a retest occurs. |
| Anomaly route | One route for capture, triage, impact, decision, corrective action, and renewed assessment. | An anomaly disposition may trigger re-verification or re-validation; it does not itself prove either has succeeded. |

Use a flow for the shared lifecycle and a compact decision or mapping table for the two assessment paths. Meaningful columns include basis, method, criterion, subject or configuration, required evidence, and disposition authority. The table states rules and roles. Additional matrices or native diagrams are optional when one clear representation preserves the two assessment questions.

## Quality criteria

- Verification and validation retain different bases, methods or scenarios, criteria, evidence links, and conclusions despite shared management steps. A shared event does not merge those conclusions.
- The independence rule is checkable as required, not required, or not established for each applicable activity class. Silence is not a decision that independence is unnecessary.
- Result-classification rules bind an attempted assessment to its configuration and method. An invalidating condition, an inconclusive attempt, a gap, or a `not-run` entry cannot support a pass, and a retest retains the earlier attempt and result.
- Reports state coverage and limitations truthfully, distinguish a technical finding from an authorized acceptance decision, and route anomalies back to the affected baselines and assessments.
