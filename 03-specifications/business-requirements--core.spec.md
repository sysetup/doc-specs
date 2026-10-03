# Business requirements specification

## Identity and selection

- **Specification ID:** `BUSINESS-REQUIREMENTS@core`.
- **Purpose:** State the business-level obligations and constraints needed to achieve authorized business or mission outcomes, with their basis, applicability, and assessment conditions.
- **Intended readers:** Business authorities, stakeholder representatives, analysts, project leads, and reviewers who derive, authorize, implement, or assess business requirements.
- **Decision or action supported:** Readers can determine what the business must achieve or observe, why each obligation exists, which obligations are authorized, and what evidence would support assessment.
- **Use when:** Business or mission objectives must be translated into identifiable business-level obligations, including clearly marked proposals awaiting authority.
- **Scope boundaries:** State obligations at the level of business actors or functions and assessable business outcomes or operating rules. Limit implementation choices to constraints expressly established by a project decision.

## Authoring inputs and unresolved facts

Obtain the business or mission boundary and intended outcomes; the inspected project need statements, sponsor decisions, allocations, established operating limits, or delivery commitments forming the basis of each proposed obligation; the project role that can decide its content; and relevant business processes, value flows, stakeholder interests, information dependencies, and operating conditions. Obtain the project's requirement-control vocabulary and existing controlled requirement or relationship records, identifying each obligation's established ID and wording. Determine how each obligation could be assessed at the business level, and which thresholds, priorities, approvals, and downstream allocations are actually established.

If a need, project decision role, threshold, business rule, method, or decision is unknown, record the gap, its effect on the affected requirement, the resolving action, and the actual owner if assigned. Identify each sponsor decision or supplied project delivery commitment by its actual scope and controlled edition or decision identity. Keep an unapproved or incompletely assessable statement visibly proposed; it MUST NOT be presented as an authorized obligation. Omit an inapplicable context category after assessment rather than filling it with generic prose. Do not invent requirement IDs, approval references, method records, or implementation results.

## Finished-document contract

- **Title:** Name the business or mission subject and identify the document as its business requirements specification; include the applicable edition or scope when needed to distinguish it.
- **Frontmatter:** None. Begin with the GFM title. Business scope, obligation state, and authority are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish business boundary and source basis before the authoritative requirements; put coverage, unresolved decisions, and change information after them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity, purpose, and business boundary | Required | Identify the business or mission subject, document edition or unambiguous control identity, intended outcomes, affected organization or process boundary, relevant stakeholder groups, exclusions, and actual authority or proposal state. Give enough current and intended operating context to interpret the obligations. |
| Applicable business context | Conditional when a business model, process, information flow, established internal operating rule, operational mode, scenario, lifecycle condition, or project resource or delivery limit changes a requirement's meaning | Describe only the relevant context and its project basis. Distinguish an existing business rule from a new obligation stated in this document; do not repeat the same binding requirement in narrative form. Define terms or abbreviations that would otherwise make an obligation ambiguous. |
| Business requirements | Required | Present one authoritative statement per distinct business-level obligation or constraint, each with an ID, obligated business actor or function, applicability, source, rationale where needed, and an assessable business condition. Group by business capability or outcome where useful. Identify proposal, approval, or other content state where it differs among items. Keep each statement at the business actor or function level; describe established downstream allocations through links to the identified project records. |
| Source, coverage, and assessment | Required | Show how the requirements address the inspected project needs, decisions, allocations, and established operating or delivery constraints; identify unsupported statements, gaps, conflicts, and deferred concerns. For each active obligation, state the business result, condition, measure, or threshold a later business assessment would have to observe. State the planned assessment basis without assigning an observed outcome. A real relationship view may be referenced, but it cannot replace the requirement statements. |
| Authority, unresolved decisions, and change | Required | Identify actual content endorsement or approval, its decision maker, and its scope when it exists; label review and approval separately. Record open decisions, their effect and resolution route. State how the applicable set or baseline is identified, and how a change to an obligation or its source is evaluated and communicated. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Business boundary | One coherent subject and applicability frame for the requirement set. | State the organizational, process, service, or mission scope and relevant operating conditions. Context may mention system options without allocating detailed technical behavior to them. |
| Business requirement | One or more distinct obligations; each has one stable ID unique within the controlled set. | State a single business-level outcome, capability, operating rule, or authorized constraint with an identifiable obligated actor or function and applicability condition. Use the project's normative wording consistently. Include an implementation constraint only when an identified project decision establishes it; state its business consequence and scope. |
| Source and decision authority | At least one inspected origin or documented derivation per requirement. | Identify the originating project need, sponsor decision, allocation, established operating limit, or supplied delivery commitment by usable title/ID, edition, and locator when needed. State the actual project role that can authorize derived or disputed content. A cited origin does not by itself prove that this requirement has been approved. |
| Rationale and priority | Rationale when the obligation or derivation is not self-evident; priority only when the project uses it for scope decisions. | Explain necessity and any tradeoff. Define an actual priority vocabulary locally; a priority label does not make a proposed obligation binding or waive an approved one. |
| Requirement content state | One truthful set state, with per-item state when items differ. | Use proposed, reviewed, approved, superseded, or rejected to describe the wording's authorization and currency; define additional project terms if used. Cite an actual decision for an approval claim. Do not use `pass`, `fail`, `inconclusive`, `not-run`, `verified`, or `validated` as a content state. |
| Assessment condition | One assessable basis for each active requirement, integral to or alongside its statement. | Give the expected business result, relevant conditions, units, timeframe, tolerance, or sample basis where meaningful. A qualitative rule needs an observable interpretation. State the condition a later business assessment would use without assigning `pass`, `fail`, `inconclusive`, or `not-run`. Cite an established project assessment method only when it assesses that business-level condition. |
| Downstream or interface relationship | Zero or more real links per requirement when allocation or affected interfaces have been established. | Identify the related controlled project statement or element by usable identity and version; describe the established allocation or affected interface without repeating its detailed obligation. |
| Open or deferred obligation | Zero or more proposals, disputes, exclusions, or later-scope items. | State the reason, consequence for coverage, resolving decision or action, and actual owner if assigned. A gap cannot be hidden by a plausible placeholder requirement. |

Use prose for the business context and a numbered list or compact table for obligations, with meaningful ID, statement, source, applicability, state, and assessment columns. A business process or context diagram MAY clarify relevant actors, flows, or modes, but it MUST NOT be the only authoritative expression of a requirement. A source-to-requirement view is useful for coverage; use requirement IDs to link to the stated obligations. Include project-record references or definitions where needed for interpretation, without a generic document-control block or blank category tables.

## Quality criteria

- Each active requirement stays at the business level, states one understandable obligation, has a real origin and decision authority, and can be assessed under stated conditions without guessing a threshold or actor.
- The set addresses the relevant authorized outcomes and constraints; missing, disputed, inapplicable, and deferred concerns remain visible rather than appearing silently complete.
- A business obligation appears once. Context, traceability links, downstream allocations, and assessment plans agree with its authoritative wording.
- Proposal state, authorization of each obligation, and its planned assessment basis remain explicit; an assessment condition describes expected observations without claiming they occurred.
