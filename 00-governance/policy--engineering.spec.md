# Engineering policy specification

## Identity and selection

- **Specification ID:** `POLICY@engineering`.
- **Purpose:** Establish mandatory engineering direction for lifecycle responsibility, requirements, interfaces, and the quality of technical decisions.
- **Intended readers:** Engineering roles, project and technical decision authorities, and people who depend on engineering outputs across lifecycle boundaries.
- **Decision or action supported:** Readers can identify who owns technical work and decisions, how requirements and interfaces are governed, and what basis is needed before a technical conclusion or change is accepted.
- **Use when:** An issuing authority needs broad engineering obligations for a defined organizational or project scope.

## Authoring inputs and unresolved facts

Obtain the issuing mandate, covered engineering disciplines and lifecycle boundaries, actual technical roles and decision delegations, supplied project requirements and interface ownership rules, established project needs, allocations and technical decisions, expectations for reviews and evidence, exception authority, and policy maintenance arrangements. Obtain the edition, issuance state, and effective-date decision when controlled by the project.

If a role, interface boundary, requirement authority, or technical gate is unknown, state the specific gap, its effect on the proposed obligation, the resolving action, and the actual owner if assigned. Do not invent lifecycle stages, review gates, technical results, approvals, or project decisions. A draft lacking established authority, scope, or substantive obligations MUST remain visibly proposed.

Normally all four named engineering subjects are covered. A subject may be excluded only where it is outside the issuing mandate for the stated scope. For each exclusion, record the subject, exact excluded scope, reason, actual issuing authority, explicit disposition, and decision date or locator. A pending disposition does not remove a subject or reduce its obligations; the policy MUST remain proposed until that disposition is established. Only an approved exclusion of an entire named subject reduces the coverage and directive minimum; a partial exclusion leaves that subject in scope. At least one named subject and substantive mandatory direction MUST remain. If all subjects are excluded, keep the document proposed and resolve its mandate and scope before issuance.

## Finished-document contract

- **Title:** Name the organization or project subject where needed and identify the document as an engineering policy.
- **Frontmatter:** None. Begin with the GFM title; authority, applicability, and state are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Present authority and boundaries before mandatory direction, then responsibility and exception rules, then communication and review. Headings may use local wording if the roles remain identifiable.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority, purpose, and scope | Required | Identify the real issuing authority or mark it proposed; policy owner, edition, truthful issuance state, affected disciplines and people, systems or products, lifecycle boundary, exclusions, and effective date only when established. State the engineering outcome and the project needs, allocations or decisions that establish the obligations. |
| Mandatory engineering direction | Required; subject coverage follows the approved exclusions defined above | State identifiable obligations for **lifecycle responsibility**, **requirements**, **interfaces**, and **decision quality** wherever each subject remains in scope. For those subjects, respectively govern continuity of technical accountability through the covered lifecycle; source, allocation, change, and evaluation of requirements; ownership and coordinated change of interfaces; and proportionate rationale, assumptions, risks, alternatives, and evidence for consequential technical decisions. Specify how claims of conformity to requirements and fitness for intended use are to be supported where those claims are within scope. State the required review, verification, validation, or acceptance practices where needed. |
| Technical authority and coordination | Required | For the subjects in scope, allocate responsibility and decision rights for engineering outputs, requirements and interface changes, cross-discipline conflicts, and acceptance of technical evidence. Define an escalation route when authorities or baselines conflict. State the coordination and handoff rules needed to apply these obligations. |
| Exceptions and nonconformance | Required | State whether policy exceptions are allowed. If allowed, identify decision authority, request basis, consequences, how the decision is recorded, and expiry or review rule; state what applies while a request is pending. Define routing for departures from engineering obligations. If exceptions are prohibited, state that rule and the conflict route. |
| Communication, oversight, and review | Required | State how obligations and revisions reach affected disciplines, what information is used to oversee adherence, and who reviews and changes the policy and when. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Issuing authority and policy owner | One identified issuing body or delegated role, and one maintenance role. | A technical reviewer or project manager is not automatically the issuing authority; a proposed role is labeled proposed. |
| Applicability | One explicit statement of disciplines, roles, products or systems, lifecycle stages, and material exclusions. | Do not claim authority over organizational or supplier boundaries not covered by the mandate. |
| Issuance state and edition | One truthful state and unambiguous edition; effective date only if established. | Distinguish proposed, authorized but not yet effective, effective, and withdrawn or superseded states in local terms. |
| Engineering directive | Normally four or more distinct obligations, with at least one for each named subject. Subtract one from this minimum for each approved whole-subject exclusion; retain at least one distinct obligation per remaining subject. | Give each a stable local label, addressee, required action or constraint, and applicable condition. Count a directive only once even if it covers several subjects; such coverage does not reduce the distinct-obligation minimum. Subject labels, exclusions, unresolved gaps, and aspirations do not count. |
| Requirements governance rule | When requirements remain in scope, at least one obligation covering the project need, allocation or decision underlying requirements, responsibility for allocation or change, and basis for evaluating conformity. | Identify the requirements by their actual project IDs or locators where needed. Allow the verification method to suit the requirement. |
| Interface governance rule | When interfaces remain in scope, at least one obligation identifying coordination and change authority across the actual interface boundary. | Identify an interface agreement or technical detail only when supplied as actual project data. |
| Technical decision rule | When decision quality remains in scope, at least one obligation for decision authority and proportionate documented basis. | Define how a proposed choice and review recommendation lead to an authorized decision, and what evidence is required to evaluate its outcome. |
| Exception rule | One allowance or prohibition. | A deviation request does not authorize itself; require an explicit decision by the designated authority. |

Use concise prose with numbered directives. A responsibility table MAY help when several disciplines share decisions, and a brief flow MAY clarify escalation across boundaries.

## Quality criteria

- All four engineering subjects are covered unless an explicit issuer-approved exclusion removes a subject for the stated scope. Every exclusion has its scoped reason and decision identity; pending decisions and empty governed scope prevent issuance. The distinct-directive minimum matches the remaining subjects without counting exclusions or gaps.
- Subjects in scope are governed without conflicting ownership or decision rights. Where lifecycle responsibility is covered, responsibilities remain clear at handoffs. Where requirements or interfaces are covered, their obligations preserve source, change authority, and coordination; where decision quality is covered, technical decisions have an accountable basis proportionate to their consequences.
- Requirements for verification, validation, reviews, or technical acceptance identify the required evidence and decision authority; a proposal or recommendation alone cannot establish an approved outcome.
- Each directive states mandatory engineering direction at a level usable across the covered disciplines and lifecycle boundaries.
