# Internal standard specification

## Identity and selection

- **Specification ID:** `STANDARD@core`.
- **Purpose:** Establish authorized, mandatory, assessable criteria for a defined organizational or project practice or artifact.
- **Intended readers:** People and teams subject to the criteria, assessors who check them, exception decision makers, and the standard's maintainer.
- **Decision or action supported:** A reader can determine which criteria apply, how conformity is assessed, and how an exception or revision is handled.
- **Use when:** An identified authority needs binding technical or practice criteria for a stated domain, such as engineering, security, operations, APIs, data, testing, or documentation.
- **Scope boundaries:** Each requirement states a mandatory, assessable condition for the governed practice or artifact. A definition carries an obligation only when an explicit requirement attaches one to it.

## Authoring inputs and unresolved facts

Obtain the authority to issue the standard, its subject and affected people or artifacts, scope boundaries, the proposed mandatory criteria, and the supplied project need, allocation or decision that establishes each criterion. Establish observable assessment criteria and the expected evidence or inspection basis. Obtain the actual exception authority and disposition route, the maintenance role and review triggers, and the intended edition, issuance state, and effective date when decided. Check whether a new edition changes obligations for existing work and obtain the authorized transition rule if it does.

If issuing authority, scope, or substantive criteria are not established, mark the text as proposed and identify the gap, consequence, resolving action, and actual owner if assigned; it MUST NOT claim to be in force. If a criterion is inapplicable to a stated scope, explain that scope rather than create an empty requirement or invented exception. Do not infer approval, effective date, or conformity from a drafted standard or expected evidence.

## Finished-document contract

- **Title:** Name the governed subject and identify the document as a standard; “Internal Standard” alone is insufficient.
- **Frontmatter:** None. Begin with the GFM title. Authority, applicability, and effectivity are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State authority and applicability before mandatory criteria; define terms before their first ambiguous use; put exception and maintenance rules after the criteria. Headings may use project wording if their semantic roles remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority, identity, and applicability | Required | Identify the issuing authority or mark it as proposed; state the subject, accountable maintainer, affected people, activities or artifacts, boundaries, exclusions, controlled edition or other unambiguous version, and truthful issuance state. Give an effective date only when decided by the proper authority. State the edition's issuance state and date of effect separately. |
| Terms and interpretation | Conditional when a term or interaction between criteria affects interpretation | Define terms that could change assessment and explain how ambiguities or conflicts between criteria are resolved, including the internal decision role responsible. |
| Mandatory criteria and assessment basis | Required | State one or more separately identifiable obligations. For each, give its applicability, observable assessment criterion, and the evidence type or inspection basis that would show whether it is met. State units, thresholds, tolerances, allowed values, and exact conditions where needed to make a criterion assessable. The criterion states the condition an assessment would observe, including what would meet or miss it. |
| Exceptions | Required | State whether exceptions are permitted. If permitted, give request and decision authorities, assessment conditions, scope of a decision, how the decision is recorded, expiry or review rule, and the rule while a request is pending. If prohibited, state that and identify how conflicts are raised. A request or silence is not authorization. |
| Adoption, review, and change | Required | State how the edition is identified, how changes become applicable and are communicated, and the maintainer's review cadence or triggers. When a changed criterion affects existing work, state the authorized transition, grandfathering, or remediation rule and its scope; do not assume retroactive effect or exemption. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Standard domain and scope | One governed subject with explicit affected population, activities or artifacts, conditions, and material exclusions. | A domain label such as security, API, or testing may aid discovery. Identify the specific practices or artifacts governed within that domain. |
| Issuing authority and state | One actual issuing body or delegated role, and one truthful state for the stated edition. | A draft may name a proposed authority, clearly labeled. Use project vocabulary but distinguish proposed, authorized, effective, and superseded or retired states. |
| Standard requirement | One or more distinct mandatory criteria. | Give each a stable local ID, an addressee or governed artifact, explicit obligation, applicability condition, and assessable criterion. A criterion may be expressed in prose or a table; avoid combining unrelated obligations under one ID. |
| Assessment basis | One basis per requirement, integral to or alongside its criterion. | Name what can be inspected or measured and the expected evidence type. If direct inspection of the governed artifact suffices, say so rather than requiring a separate record. |
| Exception rule | One allowance or prohibition rule. | An allowed exception needs an actual decision authority, bounded scope, record route, and expiry or review treatment. |
| Edition and transition | One unambiguous edition identifier; transition content is conditional on a changed obligation affecting existing work. | State when criteria apply only after the authority has decided. Identify the date of approval, the date of effect, and the compliance deadline separately when they differ. |
| Criterion rationale | Zero or more supplied project needs, allocations or decisions explaining a criterion. | Identify the actual project item and its locator when needed. State the mandatory criterion explicitly alongside its assessment basis. |

Numbered clauses or a compact table are suitable for the criteria if each keeps its conditions and assessment basis together. Use prose for authority, exceptions, and transitions; a short decision flow may clarify a branching exception route. Do not use blank requirement rows. Assessment criteria MUST be checkable, but a syntax check alone does not prove the truth of a conformity claim.

## Quality criteria

- Each obligation has an identifiable addressee or artifact, defined applicability, and a criterion an assessor can apply without guessing the threshold or the internal standard's edition.
- Criteria are internally consistent; definitions and interpretation rules resolve material ambiguity in their application.
- Readers can distinguish a proposed or authorized edition from one that is effective, and can tell how changed criteria apply to existing work when that question arises.
- Exception authority and scope are explicit; a waiver request, assessment result, or missing objection is not presented as an authorized exception.
- Each assessment basis names the expected evidence or inspection; a conformity claim requires the corresponding actual observations.
