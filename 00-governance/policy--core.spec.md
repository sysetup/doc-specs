# General policy specification

## Identity and selection

- **Specification ID:** `POLICY@core`.
- **Purpose:** Define authorized, mandatory, high-level direction for an organization's or project's stated general policy subject and scope.
- **Intended readers:** People bound by the policy, managers who apply it, and the authority that issues and maintains it.
- **Decision or action supported:** Readers can determine what direction applies to them, who owns it, and how an exception or change is handled.
- **Use when:** A real issuing authority needs to establish broadly applicable obligations for a stated subject and scope.
- **Scope boundaries:** Cover a general policy subject outside configuration management, cybersecurity, engineering, quality, and risk management. Keep directives at the level of organizational duties, decision rights, and outcomes.

## Authoring inputs and unresolved facts

Obtain the internal issuing mandate or decision, the policy subject and affected population, applicable organizational or project boundaries, the intended obligations, the role responsible for maintaining the policy, the treatment of exceptions, and the review or change authority. Obtain established project decisions and the explicit content of supplied commitments that define directive scope, addressees, or obligations. Obtain the actual policy edition and issuance state when the project controls them.

If a fact is unknown, distinguish missing evidence from a decision that has not been made. State the gap, why it matters, the resolving action, and the actual owner if one is assigned. If a proposed clause is inapplicable, omit it or explain the boundary; do not manufacture an exception or approval. A draft without established issuing authority, scope, or substantive directives MUST remain visibly proposed and MUST NOT claim to be effective. Do not invent authority, dates, obligations, or project references.

## Finished-document contract

- **Title:** Name the policy subject and identify the document as a policy; a generic title such as “General Policy” alone is insufficient.
- **Frontmatter:** None. Begin with the GFM title. Policy authority and applicability are substantive content in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Present authority and scope before directives, and directives before exception and maintenance rules. Headings may use project wording if their semantic roles remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority and applicability | Required | Identify the actual issuing authority or mark it as proposed; identify the policy owner, controlled edition or other unambiguous version, issuance state, subject, affected people or functions, boundaries, exclusions, and effective date only when established by the proper authority. Distinguish authorization from the date a policy takes effect. |
| Purpose and mandatory direction | Required | Explain the desired outcome and state one or more clear, mandatory directives. Make the addressee and obligation discernible; group related directives without repeating them. Give rationale where it clarifies intent or a non-obvious boundary. Where a directive requires subsequent work, state that duty and its triggering condition explicitly. |
| Accountability and application | Required | State who must apply the directives, who interprets or oversees them, and how conflicts in obligations or decision rights are escalated or resolved. State the application conditions and decision bounds needed by each responsible role. |
| Exceptions | Required | State whether exceptions are allowed. If allowed, specify who may decide, the conditions and evidence for a request, the record required for the actual decision and any expiry or review, and what applies while a request is pending. If prohibited, state that rule and the route for raising a conflict. |
| Review and change | Required | Give a review cadence or concrete triggers, the role or authority for changes, and how approved changes are communicated and made effective. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Issuing authority | One identified body or delegated role with authority to issue this policy. | A draft may name a proposed authority, clearly labeled as such; it is not an issued policy. |
| Applicability | One explicit statement of the covered subject, people/functions, and organizational, project, system, or lifecycle boundaries that matter. | State material exclusions and avoid silently extending the mandate. |
| Issuance state and effective date | One truthful state; an effective date is conditional on a real effective-date decision. | Use the project's control vocabulary, but distinguish proposed, authorized but not yet effective, effective, and withdrawn or superseded states. Tie the stated version, authorization, and effective date to established issuance decisions. |
| Directive | One or more separately identifiable obligations. | Give each directive a stable local label or number and a clear addressee, mandatory action or constraint, and applicable condition. Keep the obligation at the level of high-level duties, decision rights, and outcomes. |
| Policy owner | One accountable role for maintenance and interpretation routing. | Do not confuse this role with the issuing authority unless the project actually assigns both to the same body. |
| Exception rule | One rule covering allowance or prohibition. | When exceptions are permitted, define decision authority and decision bounds; a request never grants its own exception. Require an explicit decision and a record of its scope, conditions, and expiry or review rule. |
| Project decision or commitment reference | Zero or more references to supplied project decisions or commitments that explain a directive. | State the relevant project fact explicitly and identify its actual record, version, and locator when needed. |

Use concise prose for intent and application. Numbered directives or a compact table may help readers locate obligations; a table MUST NOT turn policy into empty field rows. A short decision flow may clarify the exception route when it branches. Do not add a document-control table, signature block, or checklist unless the project requires it.

## Quality criteria

- Each directive has an identifiable addressee and can be applied within the stated scope; obligations do not contradict one another or the exception rule.
- Readers can tell whether the text is proposed, authorized but awaiting effect, effective, withdrawn, or superseded, and which edition applies.
- Directives state mandatory high-level duties, decision rights, and outcomes; keep detailed technical thresholds and operational steps outside their scope.
- Exception and change authorities are real and consistent with the issuing mandate. Project references support the facts they identify; authorization and effective dates have an established decision basis.
