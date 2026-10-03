# Cybersecurity policy specification

## Identity and selection

- **Specification ID:** `POLICY@cybersecurity`.
- **Purpose:** Establish mandatory security direction for protection objectives, secure development, incident response, and supply-chain security within an authorized scope.
- **Intended readers:** People who design, build, acquire, operate, or oversee the covered systems and information, and the policy's issuing authority.
- **Decision or action supported:** Readers can identify the security duties that apply, where to report or escalate a security concern, and who may decide a policy exception.
- **Use when:** An issuing authority needs a subject-specific policy governing cybersecurity responsibilities and outcomes across a defined organization or project.

## Authoring inputs and unresolved facts

Obtain the internal issuing mandate and established project security duties; the covered systems, information, services, people, suppliers, and lifecycle boundaries; established protection objectives, project security requirements, and risk decisions; existing security ownership and escalation authority; the actual development, acquisition, operational, incident, and supplier contexts; the supplied supplier delivery scope and agreed security responsibilities; permitted exception and risk-acceptance authorities; and policy communication and review expectations. Obtain the actual edition, issuance state, and effective-date decision when available.

If a protection objective, threat assumption, project security duty, or role is unknown, mark the decision or evidence gap and the actual resolving action and owner if assigned. For each subject area that does not apply to the stated scope, document the area, scoped reason, affected boundary, and the issuing authority's exclusion decision, including the issuer, decision date, and project decision locator, before issuing the policy. Only an approved exclusion reduces required subject coverage and the directive minimum defined below; a missing input or pending decision does not. At least one subject area must remain included. Do not silently omit a subject that belongs in the stated scope or pretend a supplier or development activity exists. A draft without established authority, scope, or substantive obligations MUST remain visibly proposed and MUST NOT claim to be effective. Do not invent security classifications, control selections, supplier commitments, approvals, or adherence findings.

## Finished-document contract

- **Title:** Identify the covered subject as a cybersecurity policy and name the organization, project, or system boundary where ambiguity would result.
- **Frontmatter:** None. Begin with the GFM title. Authority, applicability, and policy state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State authority and scope before security obligations; place responsibility and exception routes after the obligations they govern. Headings may use project wording if their roles remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority, objectives, and applicability | Required | Identify the real issuing authority or mark it proposed; policy owner, edition, truthful issuance state, covered people and assets or services, boundaries and exclusions, and effective date only when established. Explain the protection outcome and the established project security duties it addresses. |
| Mandatory security direction | Required | Account for **protection objectives**, **secure development**, **incident response**, and **supply-chain security**, stating identifiable obligations for each included area and the approved exclusion decision for each excluded area. For included areas, protection direction identifies what interests must be protected and who sets applicable priorities; development direction governs security across design, change, and release as applicable; incident direction governs recognition, reporting, escalation, decision authority, and preservation of relevant information; and supply-chain direction governs security expectations and accountability for externally supplied components or services within scope. State the required duties, decision rights, and conditions for each included subject area. |
| Security accountability and escalation | Required | Assign roles for applying the obligations, interpreting them, receiving reports, coordinating across the internal and supplier boundaries within scope, and deciding a security conflict or material risk. State who provides recommendations or risk assessments and who has the decision right, with each role's decision bounds. |
| Exceptions and noncompliance | Required | State whether exceptions are allowed; if allowed, identify decision authority, request basis including security consequence, scope, duration or review trigger, the record required for the actual decision, and interim treatment. State how suspected noncompliance is reported and addressed. If exceptions are prohibited, give the conflict route. |
| Communication, oversight, and review | Required | State how the policy and its changes reach affected roles; what kind of adherence information the responsible authority requires; how findings are escalated; and review cadence or triggers and policy change authority. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Issuing authority and policy owner | One identified issuer or delegated role, and one accountable maintenance role. | A named security team is not necessarily the issuing authority. Mark proposed assignments as proposed. |
| Applicability | One statement of affected people, systems, information, services, suppliers, lifecycle stages, and material exclusions. | For external parties, state the supplied delivery scope and agreed security responsibilities, identifying the established project agreement or decision that assigns them. |
| Issuance state and edition | One truthful state and unambiguous edition; effective date only when decided. | Distinguish draft, authorized but not effective, effective, and withdrawn or superseded in the project's terms. Tie the stated edition, authorization, and effective date to established issuance decisions. |
| Security directive | Normally four or more separately identifiable obligations, with at least one for each named subject area. With one to three approved subject exclusions, the minimum is four minus the number of excluded areas, with at least one obligation for every included area. | Give each a stable local label, addressee, required action or constraint, and applicable condition. Count each directive once even if it addresses several areas. A subject label, exclusion decision, or desired outcome alone is not a directive. |
| Protection objective | One or more scoped interests and expected protection outcomes when protection objectives are included; no objective entry is required solely for an approved exclusion of that area. | Address confidentiality, integrity, availability, privacy, safety, or other concerns only as the actual context warrants; do not assign a classification or priority without a basis. |
| Incident escalation rule | At least one rule naming the report destination or role, coordination authority, and information-handling expectation when incident response is included; no incident rule is required solely for an approved exclusion of that area. | A time or channel may be stated when it is itself an organization-wide duty. Keep the rule at the level of reporting, coordination, decision rights, and protection of relevant information. |
| Exception and risk decision rule | One allowance or prohibition and a real decision route. | Acceptance of security risk requires an explicit recorded decision by the actual designated authority. State the required decision basis, scope, conditions, and duration or review trigger. A request, review, or absence of action is not acceptance. |
| Project security requirement or decision reference | Zero or more references or mappings to supplied project security requirements or decisions. | State the relevant duty or decision explicitly and identify the actual project record, version, and locator when needed. Limit claims about implementation or observed outcomes to established evidence. |

Use prose and numbered directives. A compact role or reporting-path table MAY clarify multiple authorities; a short flow MAY clarify incident escalation or exception routing.

## Quality criteria

- Each of the four subject areas has either obligations identifying the responsible actor and decision path or a documented exclusion approved by the issuing authority. Directives meet the stated minimum and cover every included area; exclusions do not count as directives. Security duties across project and supplier boundaries within scope are consistent with the explicit responsibilities established for each party.
- Readers can identify where to report a policy conflict and who may decide its disposition; when incident response is included, they can also identify the incident report destination and disposition authority. Exception and risk-acceptance authority is explicit and consistent with the issuing mandate.
- Protection objectives express intended outcomes; any claim about implemented controls or observed results has established supporting evidence. Issuance, exception, and risk-acceptance states reflect actual decisions.
- Detailed technical criteria, project schedules, response branches, and implementation evidence remain outside this high-level policy. A time or channel stays here only when it is itself an organization-wide duty.
