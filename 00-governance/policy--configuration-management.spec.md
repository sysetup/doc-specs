# Configuration management policy specification

## Identity and selection

- **Specification ID:** `POLICY@configuration-management`.
- **Purpose:** Establish mandatory direction for identifying controlled configuration items, governing baselines and changes, and maintaining configuration integrity.
- **Intended readers:** People who create, change, release, use, or oversee controlled configurations, and the authority that issues the policy.
- **Decision or action supported:** Readers can determine what must be controlled, who can establish or change an approved baseline, and how unauthorized or exceptional changes are handled.
- **Use when:** An issuing authority needs organization or project-wide configuration management obligations for a defined scope.

## Authoring inputs and unresolved facts

Obtain the actual internal issuing mandate and established project decisions defining configuration management duties; the population, systems, information items, lifecycle stages, and organizational boundaries in scope; the intended classes of controlled items and baseline decisions; existing change and release decision rights; integrity and status-accounting expectations; exception and noncompliance authority; and the policy owner and review triggers. Obtain the project's definitions of a baseline and configuration item, and the explicit content of supplied commitments that affect item control, change, or release. Obtain the policy edition, issuance state, and effective-date decision when controlled by the project.

If an input is unknown, distinguish a missing project fact from a decision not yet made. State the gap, its effect on the proposed rule, the resolving action, and the actual owner if assigned. For each of the four subject areas genuinely outside the mandate, document the area, scoped reason, affected boundary, and the real issuing authority's exclusion decision, including the issuer, decision date, and project decision locator, before issuing the policy. Only an approved exclusion reduces required subject coverage and the directive minimum defined below; a missing input or pending decision does not. At least one subject area must remain included. A draft lacking established authority, scope, or substantive obligations MUST be visibly proposed and MUST NOT claim to be effective. Do not invent controlled items, authority assignments, baseline states, approvals, or project references.

## Finished-document contract

- **Title:** Identify the governed subject as a configuration management policy and, when needed, the organization or project it covers.
- **Frontmatter:** None. Begin with the GFM title. Authority, applicability, and policy state are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish authority and applicability before obligations; state obligations before exception and maintenance rules. Headings may use local wording if the roles below remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority, purpose, and applicability | Required | Identify the actual issuing authority or visibly proposed authority; policy owner; controlled edition and truthful issuance state; covered people, functions, systems or item classes, lifecycle boundaries, and exclusions. State the desired governance result and effective date only when decided by the proper authority. |
| Configuration management direction | Required | Account for **configuration identification**, **baselines**, **change authority**, and **integrity**, stating identifiable mandatory obligations for each included area and the approved exclusion decision for each excluded area. For included areas, define respectively which classes of items must be identified and under what authority; when a baseline is established or released and how its identity is known; who may authorize a change and what impact must be considered; and how approved state, actual state, and discrepancies are accounted for. Express obligations as duties, decision rights, and conditions for controlled work. |
| Accountability and decisions | Required | For the included subject areas, allocate who applies the policy, who maintains the authoritative configuration information, who may approve a baseline or change, and who escalates conflicts. State how urgent changes are governed if they are allowed; urgency alone MUST NOT be presented as authorization. State each role's decision bounds and the escalation route for conflicting assignments. |
| Exceptions and noncompliance | Required | State whether exceptions are permitted. If permitted, give decision authority, request basis, scope and duration or review rule, the record required for the actual decision, and treatment while pending. Define how suspected unauthorized changes or baseline discrepancies are escalated. If exceptions are prohibited, state the rule and conflict route. |
| Communication, assurance, and review | Required | State how obligations and approved changes reach affected roles; who checks adherence or receives status and discrepancy information; the response authority for noncompliance; and review cadence or triggers and change authority. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Issuing authority and policy owner | One real issuing body or delegated role, and one accountable maintenance role. | A proposed issuer is labeled as proposed; an owner does not gain issuing power by being named. |
| Applicability and controlled-item boundary | One explicit statement of affected people, systems, information or asset classes, lifecycle stages, and material exclusions. | If item-by-item selection is delegated, state who decides and the explicit item classes, inclusion conditions, and exclusions that bound that decision. |
| Issuance state and edition | One unambiguous edition and truthful state; effective date only if established. | Distinguish a proposed draft, an authorized policy awaiting effect, and an effective or withdrawn policy using the project's real control vocabulary. Tie the stated edition, authorization, and effective date to established issuance decisions. |
| Policy directive | Normally four or more separately identifiable obligations, with at least one governing each of the four named subject areas. With one to three approved subject exclusions, the minimum is four minus the number of excluded areas, with at least one obligation for every included area. | Give each a stable local label, addressee, required action or constraint, and applicable condition. Count each directive once even if it addresses several areas. Multiple directives may address a subject; a subject label, exclusion decision, or desired outcome alone is not a directive. |
| Baseline or change decision rule | At least one rule for establishment or release when baselines are included, and one for authorization of changes when change authority is included; no rule is required solely for an area with an approved exclusion. | For included areas, define the authorization required for each controlled state transition. When change authority is included, distinguish a requested change, its impact assessment, the decision, and the resulting controlled state; specify emergency treatment only if relevant. |
| Exception rule | One allowance or prohibition with a decision route. | A request or risk assessment does not grant its own exception. Require an explicit decision by the designated authority and a record of its scope, conditions, and duration or review rule. |
| Project decision or commitment reference | Zero or more references to supplied project decisions or commitments that explain an obligation or decision right. | State the relevant project fact explicitly and identify its actual record, version, and locator when needed. |

Use concise prose and numbered directives; a compact table MAY clarify item classes or decision rights when several roles are involved. A short decision flow MAY clarify normal and urgent change routes. A document-control table or checklist is optional when useful for identifying or applying the policy's duties and decision rules.

## Quality criteria

- Each of the four subject areas has either real, applicable obligations or a documented exclusion approved by the issuing authority. Directives meet the stated minimum and cover every included area; exclusions do not count as directives. Identification, baseline, change, and integrity rules within scope work together without contradictory decision rights.
- When baselines are included, baseline rules identify the approval needed to establish controlled state, the information needed to account for actual state, and the route for a discrepancy or unauthorized change.
- Authority, edition, scope, exception path, and effective state are consistent with actual decisions. Review and communication rules make a change to the policy usable by affected roles.
- Directives specify high-level configuration management duties, decision rights, conditions, and outcomes; keep project scheduling, detailed tool steps, and item-by-item inventories outside their scope.
