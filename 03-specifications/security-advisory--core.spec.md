# Recipient security advisory specification

## Identity and selection

- **Specification ID:** `SECURITY-ADVISORY@core`.
- **Purpose:** Communicate supported vulnerability applicability and recipient actions across affected and fixed product versions.
- **Intended readers:** Affected recipients, administrators, integrators, support teams, and release or security coordinators.
- **Decision or action supported:** Determine whether the published issue applies and what established update or mitigation to take.
- **Use when:** A product security issue requires controlled communication to recipients.
- **Scope boundaries:** Describe recipient-facing applicability, impact, remediation, and advisory revisions; exclude internal case closure, attack instructions, unsupported exploitation claims, and automatic publication authority.

## Authoring inputs and unresolved facts

Inspect product and issue identity, advisory identifiers only when assigned, each affected, not-affected or unknown range and its bounds, fixed-version availability separately from status, impact and exploitation evidence, every independent assessment's context, scheme, edition, inputs, source and limits, each action and whether effectiveness was demonstrated, disclosure authority and revision history, and, for every selected native export, its schema, version, artifact, mapping, validator and check status.

Expose unknown identity, range, fix, impact, assessment input, export check or publication authority with its consequence, resolving action and assigned owner only. Unknown applicability is not not-affected. A missing assessment input stays unresolved and is not filled from another scheme. Unverified remediation cannot be promised effective. Missing disclosure authority blocks an authorized-publication claim. A failed, changed or not-run export check blocks that export and is not inherited from another artifact. Do not invent identifiers, scores, exploitation, fixes, acknowledgments, disclosure permission, release outcomes or schema validity.

## Finished-document contract

- **Title:** Identify the product and security issue and name its recipient security advisory.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, publication state and native check status belong in the body. Governing source: Type-owned SECURITY-ADVISORY@core policy; no external publication metadata schema is selected.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State issue identity and applicability before impact and each independent assessment. Place recipient action and limits before publication history. Place each selected native binding after the human statements it maps. Heading wording may vary.
- **Presentation:** Required roles may share concise paragraphs, tables or lists when every range, assessment, action and selected export remains separately retrievable. Use one applicability table and one account per assessment or export. Do not add an administrative chapter for each scheme.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Human advisory (standalone) | The finished advisory owns one H1 that identifies the product, the security issue and the recipient security advisory. No YAML frontmatter is used. Edition, publication state, disclosure authority and native check status stay in the body. | GFM states applicability, assessments, actions and history. Status tokens stay exact. Bind statements to inspected evidence and actual checks. Reassess after a changed source, input, artifact or schema version. Historical claims stay attached to their edition. |
| Selected export (native) | A native artifact does not replace the human H1. Schema identity is carried by the selected artifact. Fields follow the selected schema version only. Missing native fields stay missing rather than being filled from prose. | Each selected schema and version controls its own syntax. Selecting no published schema does not adopt CSAF, CVSS or OSV. Validator status applies only to the checked artifact, schema version and mapping. The GFM text and any other export do not establish that result. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Advisory identity and communication scope | Required | Identify the product, issue and established advisory identifiers or gaps, audience, one current advisory edition and as-of point, draft, published, corrected or withdrawn state, disclosure limits and the client or receiving-party element. State that the advisory does not close an internal case, coordinate vulnerability response, reproduce upstream notice text or give attack instructions. A draft becomes published only after authorized issuance. Do not name an unassigned party, owner or authority. |
| Affected and fixed applicability | Required | State affected, not-affected or unknown for every addressed version or configuration, with evidence and boundary interpretation. State fixed-version identity and actual availability separately from that status. Prerelease, backport and unsupported-line statements need an established basis. Unknown is never not-affected. |
| Impact and assessment basis | Required | Explain recipient consequence, preconditions, known exposure limits and exploitation evidence or uncertainty, without procedural attack instructions. Repeat each independent severity assessment by product or deployment context, scheme, scheme edition, inputs, source and limits. Keep each result with that assessment. Do not replace separate assessments with a composite score or invent a missing input. |
| Recipient action and limitations | Required | Give each established update or mitigation, with applicable range, prerequisites, source, expected protection and limitations, or state that no remediation is established. Distinguish an available fixed release, a proposed action, an applied treatment and demonstrated effectiveness. Do not promise that an unsupported proposal is effective. |
| Publication, corrections, and references | Required | Record actual issuance and revision history, or state that publication has not occurred. Name a deciding authority only when one is established. Preserve an earlier applicability claim when a later edition corrects it. Keep support routes and references within the disclosed audience. Missing disclosure authority blocks an authorized-publication claim. Revision does not close an internal case. |
| Native advisory binding | Conditional when one or more machine-readable advisory exports are selected | For each selected export, identify the schema and version, controlling artifact, human-to-native mapping, generation inputs, validator and actual check status, including fail, inconclusive or not-run. Preserve unknown fields. A check result validates only that artifact and scope. A changed schema, version, artifact, mapping or input needs a new check before reuse. GFM prose establishes no schema conformance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Advisory edition | Exactly one current edition and publication-state account in Advisory identity and communication scope. | Use draft, published, corrected or withdrawn only with evidence. Later correction or withdrawal keeps the earlier history. Revision does not create case closure or disclosure permission. |
| Applicability range | One or more product-version or configuration entries in Affected and fixed applicability. | Each entry is affected, not-affected or unknown, with its basis and boundary semantics. Fixed-release availability is a separate fact. |
| Impact account | Exactly one impact account in Impact and assessment basis. | Bind it to evidence, preconditions and exposure limits. Keep exploitation uncertainty visible and include no procedural attack instructions. |
| Severity assessment | Zero or more independent assessments in Impact and assessment basis. | Each names one context, scheme, scheme edition, inputs, source and limits. Record a result only from those inputs. Different context or scheme values stay separate, and a missing input leaves that assessment unresolved. |
| Remediation route | One or more actions, or one explicit statement that no remediation is established, in Recipient action and limitations. | Each action names its range, prerequisites, source and limitations. Keep available fixed release, proposed action, applied treatment and demonstrated effectiveness distinct. |
| Disclosure and revision event | Zero or more actual events in Publication, corrections, and references. | Each event identifies its authority or the absence of authority, its time precision or a stated timing gap, the affected edition and the public or restricted scope. Keep drafting history distinct from issuance. |
| Native export | Zero or more selected export bindings in Native advisory binding. | Each states its schema, schema version, artifact, mapping, generation inputs, validator and checked scope. One binding does not inherit another binding's check, and omitted native fields stay omitted. |

Use plain recipient language, one applicability table, a separate account for every assessment and selected export, an action list and a short correction history. The human advisory controls recipient communication. Each checked native artifact controls only its own machine-readable claim. Internal vulnerability records, vulnerability-response playbooks and third-party notices keep case closure, response coordination and upstream notice text.

## Quality criteria

- Identity, audience, edition, disclosure scope and publication state match actual evidence, and no unassigned authority or party is invented.
- Every addressed range is affected, not-affected or unknown with an interpretable boundary and source, and unknown is never recorded as not-affected. Fixed availability stays separate from that status.
- Impact keeps its conditions and uncertainty, and every severity assessment keeps its own context, scheme, edition, inputs, source, limits and result or unresolved state, without a composite substitute.
- Recipient actions are established routes or an explicit gap, and available release, proposal, applied treatment and demonstrated effectiveness remain distinct.
- Publication and corrections preserve real authority, event history and earlier claims, and missing disclosure authority blocks an authorized-publication claim.
- Each selected native export names its schema, version, artifact, mapping, validator and own check status. One result does not validate another export, and GFM does not establish published-schema conformance.
