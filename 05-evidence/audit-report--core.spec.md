# Audit report specification

## Identity and selection

- **Specification ID:** `AUDIT-REPORT@core`.
- **Purpose:** Record one audit or assessment that was performed, including its authority, scope, criteria, evidence examined, findings, limitations, and conclusions.
- **Intended readers:** The audit client, the auditee, the audit team, and anyone who later relies on what was examined and what the evidence supports.
- **Decision or action supported:** See which criteria were applied, which evidence supports each finding, what remains outside the conclusion, and which follow-up exists.
- **Use when:** An audit or assessment has been performed and its scope, criteria, inspected evidence, findings, limitations, and dispositions must be recorded without inventing compliance.
- **Scope boundaries:** Report examination work actually performed and conclusions supported by the examined evidence. Planned work and unexamined scope cannot be presented as completed assessment.

## Authoring inputs and unresolved facts

Obtain the project's assignment authorizing the audit; the client, auditee, and team; the competence, independence, and conflict facts that are known; the objectives and the decisions the audit was intended to inform; the organizations, processes, sites, period, and exclusions; the concrete criteria actually applied and their supplied project requirement or decision basis, revision, locator, and assessed scope; the methods, dates, sampling or coverage basis, and any deviation from a plan that was actually used; the evidence examined, with locators and integrity or access limits; the findings and the explicit classification definitions actually used; auditee responses that were received; the conclusions the evidence supports; follow-up that exists; and distribution, confidentiality, issue approval, and retention when those facts are known.

If authorization, a criterion, evidence, independence, or a classification definition is not established, state that gap. Do not invent a requirement, an observation, a conflict clearance, a due date, a cause, or an effectiveness result. A criterion must state the condition assessed; a name or citation alone is insufficient. Record only work actually performed and derive conclusions from this audit's examination. Cite a project plan, control record, action, approval, or assessment event only when it exists and supports an identified fact.

## Finished-document contract

- **Title:** Name the audited subject and identify the document as an audit report.
- **Frontmatter:** None. Begin with the GFM title. Identity, criteria, findings, and conclusions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State objectives and scope before the method and the evidence. State findings before conclusions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Audit identity, objectives, and scope | Required | Identify one performed audit or assessment. State who authorized it and the assigned examination scope, or that authorization is not established. Identify the client, auditee, and team, and the competence, independence, and conflict facts that are known. State the objectives, the decisions the audit was intended to inform, and the organizations, processes, sites, period, and exclusions. State the exact criteria and the project need or decision establishing their assessed scope. |
| Method, evidence examined, and limitations | Required | State the methods, dates, and places actually used, the sampling or coverage basis, and any deviation from a plan that was followed. Identify the evidence examined, with source, date, and locator, and the integrity or access limits. State what was not examined. A completed checklist is not itself the evidence. |
| Findings | Required | Give one finding for each classified result this audit reports. When the stated scope was assessed and no finding is reported, say so and include no placeholder finding. |
| Conclusions, follow-up, and distribution | Required | State conclusions limited to the scope, criteria, and evidence. State the follow-up that exists, or that none applies or none is recorded. State recipients, confidentiality, any approval to issue this report, and retention when that fact is known. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Audit identity | One performed audit or assessment. | Bind it to the subject and the period examined. A later follow-up audit has its own identity and examination period. |
| Authorization | One statement of the authority used, or that authority is not established. | Work without established authorization may be recorded only if the report says it was not an authorized audit. Do not invent a client or a mandate. |
| Parties | One account of the client, auditee, team, and known competence, independence, and conflicts. | If one organization fills more than one of these roles, say so. Silence is not independence and is not a conflict clearance. |
| Criteria | One or more criteria actually applied. | State each required condition and the evidence needed to assess it. Identify its supplied project requirement or decision basis, revision, relevant entry, locator, and assessed scope when established; state any basis gap. Criteria that were intended but not applied are listed as not applied. |
| Method | One account of the work done. | Include the dates and either the sampling basis or an explicit statement that sampling was not used. Cite an audit plan only when one was followed, and record deviations from it. |
| Evidence examined | The sources actually inspected, or an explicit statement that no evidence could be obtained. | Give a reproducible locator and the integrity or access limit. A planned source that was not inspected is not evidence. Do not copy secrets into the report; cite the controlled location and the access limit. |
| Coverage limit | One statement for the audit. | Name what the examination supports and what it does not. Do not extend a finding or a conclusion to an unexamined site, period, process, or population. |
| Finding | Zero or more. One row or block each. | Zero is allowed only after the scope was assessed. Each finding has a local label or a real project identifier, the criterion, the observed fact and locator, the class, and the comparison. Do not invent a global identifier pattern. |
| Finding class | One class for each finding, using the explicit classification definitions this audit adopted. | Use `conformity`, `nonconformity`, `observation`, `opportunity`, or `undetermined` when these definitions were adopted: `conformity` means the identified evidence meets the stated criterion; `nonconformity` means it does not; `observation` is noteworthy without establishing either; `opportunity` is a possible improvement without an unmet criterion; `undetermined` means the criterion, evidence, or classification definition is insufficient to classify. If no classification definitions were adopted, use `undetermined` and say that. When the project used another set, state each class's meaning and assignment condition and the class assigned. Do not relabel an unmet criterion as an observation or an opportunity. |
| Finding assessment | One comparison for each finding. | State the extent and the uncertainty. Record an auditee response only when one was received; otherwise say that none was received. |
| Action reference | Zero or more for each finding. | Cite a real corrective or follow-up action, with its identity and locator. A nonconformity with no action says that none is recorded. |
| Conclusion | One or more statements. | Limit each statement to the criteria and evidence identified, including uncertainty and coverage limits. A completed checklist or absence of nonconformity findings alone does not establish that every criterion was met. |
| Follow-up | One statement for the report. | When a finding needs correction or a later check, state the responsible party if one is assigned, any due information that exists, and whether correction, cause analysis, or effectiveness verification has occurred. If it has not, say so. Do not invent a date, a cause, or an effectiveness result. When no follow-up applies, say that. |
| Distribution | One statement for the report. | Name the authorized recipients and the confidentiality limit. Cite approval to issue this report only when that approval occurred. State retention when it is known. |

Use prose for scope, method, limits, and conclusions. Use one row or block per finding so the criterion, evidence, class, and assessment stay together. Do not add a blank row, a generic document-lifecycle block, or an identifier pattern.

## Quality criteria

- Every `conformity` or `nonconformity` states the criterion, identifies its project basis revision and locator, and identifies the evidence examined. Missing criterion, basis identification, or evidence requires `undetermined`.
- The coverage limit stays attached to the conclusion. The report does not claim conformity for an unexamined part of the scope.
- Authorization, independence, conflicts, and auditee response are written as known or not established. The existence of the report does not supply them.
- Follow-up that has not happened is not written as complete. Finding closure needs the actual correction or check evidence required by the recorded follow-up conditions.
- Each finding class follows the stated classification definitions, and each conclusion follows the recorded comparison of criterion and evidence.
- Every cited project record exists and supports the fact for which it is cited.
