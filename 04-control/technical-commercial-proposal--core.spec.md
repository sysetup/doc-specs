# Technical and commercial proposal specification

## Identity and selection

- **Specification ID:** `TECHNICAL-COMMERCIAL-PROPOSAL@core`.
- **Purpose:** Present a bounded engineering offer with scope, deliverables, estimates, price, and proposed terms.
- **Intended readers:** Prospective clients, technical and commercial leads, procurement reviewers, and authorized negotiators.
- **Decision or action supported:** Assess or negotiate an engineering offer before an agreement establishes commitments.
- **Use when:** Study, development, integration, or maintenance work is offered to an identified receiving party.
- **Scope boundaries:** Control an engineering offer and its quotation basis; exclude internal work planning, unilateral authorization, executed agreements, and invented legal terms.

## Authoring inputs and unresolved facts

Obtain the requesting context, recipient and proposer, offering authority, offer revision, need and scope, deliverables and exclusions, technical assumptions, milestones, client dependencies, effort and cost estimation basis, pricing model, currency, tax disposition when established, validity, payment proposal, and approved source terms.

Expose unresolved scope, authority, estimate, currency, tax treatment, validity, rights, or commercial terms with consequences, resolving action, and assigned owner if known. Mark every unagreed term as proposed; unresolved material pricing or authority prevents presenting a firm authorized quotation. Do not invent legal clauses, tax rates, prices, signatures, acceptance, or client commitments.

## Finished-document contract

- **Title:** Identify the offered work and name its technical and commercial proposal.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State offer identity and need before scope and approach; establish assumptions before milestones and quotation; place proposed conditions and response route last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Offer identity and decision context | Required | Identify proposer, named recipient and relationship, subject, offer revision, date or gap, current offer state, offering authority or gap, and the problem the offer addresses. Include the client or receiving-party element. |
| Scope, deliverables, and approach | Required | State included and excluded work, deliverables, technical approach, supplied inputs, responsibilities, and proposed assessable completion or receiving criteria. Identify dependencies and assumptions rather than promising unsupported feasibility. |
| Milestones and estimate basis | Required | Give milestones, dependencies, resource and effort assumptions, estimate method and uncertainty, client inputs, and schedule basis. Distinguish forecast from proposed commitment and consumed effort from estimated work. |
| Quotation and proposed conditions | Required | State pricing model, priced scope, amounts or explicit unresolved quotation, currency, units, inclusions, exclusions, tax and payment disposition, validity, and change assumptions when established. Reconcile line items and total; reference approved source terms without inventing rights or obligations. |
| Negotiation and supersession route | Required | Give the actual response route, authorized negotiation or acceptance mechanism if established, open issues, applicable source terms, and previous-offer supersession. State that agreement and delivery authorization require their actual decision mechanism; quote submission alone does not establish them. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Offer revision and state | Exactly one revision and one state in Offer identity and decision context. | Use draft, issued, superseded, withdrawn, or expired; issuing requires actual offering authority and issued content. Draft may be issued or withdrawn; issued may be superseded, withdrawn, or expired with actual basis. Revised offers receive a new revision; client agreement is recorded separately. |
| Offered deliverable | One or more in Scope, deliverables, and approach. | Each identifies scope, proposed completion basis, responsibilities, and dependencies; exclusions remain explicit. |
| Milestone and estimate | One or more milestones and one estimate basis in Milestones and estimate basis. | State units, assumptions, source and uncertainty; unknown duration or cost is not zero. |
| Price line and total | Zero or more priced lines and exactly one total or quotation gap in Quotation and proposed conditions. | Identify currency, quantity, unit price or lump-sum basis, included charges, and rounding where relevant; taxes and exchange assumptions require established sources. |
| Term and response mechanism | Zero or more sourced proposed terms and exactly one response route in Negotiation and supersession route. | Distinguish proposed terms from agreed terms; only authorized source text or reviewed terms support rights and contractual effect. |

Use prose for the offer and assumptions, tables for deliverables, milestones, and priced lines, and direct source references for established terms. Sensitive commercial detail may use access-controlled attachments with clear scope. The proposal controls the offer; any later agreement controls actual commitments. This contract does not prescribe jurisdiction-specific legal language.

## Quality criteria

- Offer identity, revision, recipient, state, and offering authority match the actual issue or draft position.
- Deliverables, exclusions, responsibilities, dependencies, and completion proposals define the offered work.
- Milestones and estimates have explicit units, assumptions, sources, and uncertainty.
- Quoted lines and totals reconcile within stated currency and pricing scope; unresolved pricing and tax facts remain visible.
- Terms and response routes retain actual authority, validity, and supersession; proposal issue is not agreement or delivery authorization.
