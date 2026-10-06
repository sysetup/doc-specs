# Contracted engineering work agreement specification

## Identity and selection

- **Specification ID:** `CONTRACTED-WORK-AGREEMENT@core`.
- **Purpose:** Control the terms, parties, revisions, and decision state of contracted study, development, or maintenance commitments.
- **Intended readers:** Authorized client and supplier representatives, contractual and legal reviewers, project leads, and receiving maintainers.
- **Decision or action supported:** Determine which work, commercial terms, receiving criteria, and change rights are proposed or actually agreed.
- **Use when:** Engineering work requires a negotiated agreement between established parties.
- **Scope boundaries:** Maintain one contractual commitment set and its controlling execution and amendment sources; exclude offers alone, internal plans, invented signatures, jurisdiction-specific boilerplate, and legal-validity certification.

## Authoring inputs and unresolved facts

Obtain party identities and capacities, actual negotiation and execution authority, approved source terms and applicable legal-review basis, work scope, deliverables, responsibilities, acceptance arrangements, pricing and payment, dependencies, support and end-of-work provisions, agreement revision, execution mechanism and evidence when present, governing venue or jurisdiction only when established, and amendment records.

Expose unresolved parties, authority, controlling revision, scope, price, rights, acceptance mechanism, or legal-review basis with their consequence, resolving action, and assigned owner if known. Such gaps prevent presenting the affected commitment as effective or the agreement as ready for execution. A draft may preserve proposed terms but MUST NOT claim signatures or enforceability. Use supplied or authorized terms and route unknown rights for competent review.

## Finished-document contract

- **Title:** Identify the parties and work and name the document as its contracted engineering work agreement.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify parties and authority before commitments; put deliverables and receiving criteria before commercial terms; place rights, change, ending, and execution state last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Agreement identity, parties, and authority | Required | Identify the work, parties and capacities, client relationship, agreement revision, control boundary, authorized representatives or authority gaps, and any controlling executed source. State governing-law or jurisdiction facts only when actually supplied. |
| Work, deliverables, and responsibilities | Required | State included and excluded study, development, or maintenance work, deliverables, versions or configuration boundaries, party inputs and responsibilities, dependencies, and agreed or proposed milestones. Identify annexes and their revisions when used. |
| Receiving, acceptance, and support | Required | State delivery method, assessable receiving and acceptance criteria, review roles and periods when established, handling of unmet criteria, and support or maintenance scope. Separate receipt, technical checks, acceptance decisions, and payment triggers. |
| Commercial and rights terms | Required | Record actual proposed or agreed price model, currency, charge scope, payment triggers, confidentiality, data and intellectual-property treatment, licensing, warranties, liabilities, and other material terms only from authorized source text or reviewed negotiations. Unknown terms remain open; do not generate default legal clauses. |
| Change, suspension, and ending | Required | Define the actual amendment, scope-change, escalation, dispute, suspension, termination, handoff, data disposition, and support-ending provisions from the agreement basis. Identify who may decide each change and its effect on schedules and charges; expose unresolved provisions. |
| Execution, effectivity, and source precedence | Required | State current agreement state, the exact terms and annex revisions, controlling record and conflict precedence, execution mechanism and actual evidence when executed, effective dates or conditions, amendments, and remaining gaps. Preserve superseded commitments and do not equate a typed name or document delivery with execution. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Agreement revision and state | Exactly one current revision and one state in Execution, effectivity, and source precedence. | Use draft, agreed-pending-execution, executed, superseded, or ended. Draft may become agreed-pending-execution after actual agreement; that state may become executed only with the established execution mechanism and evidence. Changes require a new controlled revision or actual amendment; superseded and ended preserve their prior effectivity. Not every executed agreement is yet effective; state conditions separately. |
| Contracting party | Two or more established parties in Agreement identity, parties, and authority. | State capacity and representative authority; named contacts do not establish power to bind a party. |
| Work commitment | One or more in Work, deliverables, and responsibilities. | Each names responsible party, deliverable, configuration or scope, timing basis, and dependencies with proposed or agreed state. |
| Receiving criterion | One or more criteria in Receiving, acceptance, and support. | Identify observable condition and actual deciding role or gap; technical conformity and delivery receipt are not automatic contractual acceptance. |
| Commercial or rights term | One account per material term in Commercial and rights terms. | Preserve authorized wording and source; unknown rights, exclusions, or jurisdictions require review rather than guessed boilerplate. |
| Amendment or ending provision | One route for each applicable change or ending concern in Change, suspension, and ending. | Use the real agreement's decision rights and limits; a unilateral plan does not amend commitments. |
| Execution and controlling-source basis | Exactly one account in Execution, effectivity, and source precedence. | Identify source, exact revision, executed annexes, authority, mechanism, effectivity, and amendment precedence; a GFM summary cannot silently replace the signed or otherwise controlling agreement. |

Use GFM prose and commitment tables when they clarify responsibilities and criteria. Preserve controlling signed or native agreements and authorized legal text by exact reference and revision. Identify whether the GFM document is the proposed terms, an executed controlling text under an established mechanism, or a companion summary; only the established agreement mechanism confers effect.

## Quality criteria

- Parties, capacities, authority, and exact agreement state are grounded in actual negotiation and execution sources.
- Work scope, exclusions, deliverables, dependencies, and milestones retain their proposed or agreed state.
- Receiving and acceptance criteria name their actual decision mechanism and do not equate receipt, technical checks, and acceptance.
- Commercial and rights terms come from authorized sources; no invented legal terms, signatures, or enforceability claims appear.
- Amendment, dispute, suspension, ending, and source precedence preserve authority, effectivity, and prior revisions.
