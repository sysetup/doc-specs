# Host document authoring profile specification

## Identity and selection

- **Specification ID:** `DOCUMENT-AUTHORING-PROFILE@host`.
- **Specification edition:** `1.0`.
- **Purpose:** Declare a host's reusable document-authoring values, actor assignments, authority boundaries, and conventions for inclusion in other documents.
- **Intended readers:** Host document authors, accountable maintainers, reviewers, and the authorities responsible for the declared assignments.
- **Decision or action supported:** Determine which declared values and responsible actors apply to authoring for one host and which decisions remain specific to each document.
- **Use when:** One host needs a reusable source of document-personalization values agreed for that host.
- **Scope boundaries:** Declare authoring items for one identified host; exclude document-type contracts, publication procedures, access grants, per-document approvals, profile change or use records, and incident histories.

## Authoring inputs and unresolved facts

Obtain the host identifier and applicability, organizational context or assessed absence, profile identity and own edition, actual maintainer, declared actors with names, positions and nonsecret internal IDs, applicable role assignments and decision rights with their actual bases, and agreed authoring and handling conventions. Obtain established process or service responsibility references only when they affect these assignments. Distinguish future target-document facts from reusable conventions.

For an unknown, undecided, conflicting, or inapplicable value, state the missing fact or assessed exclusion, its consequence, the resolving action, and the actual owner if assigned. Keep unresolved identity, mandate, or scope visibly blocked for the affected use; no file location, current date, generic role, account, or source digest supplies the missing fact. Values applied to a target document require resolved applicable declarations; never invent a person, ID, approval, event, source edition, or observed result.

## Finished-document contract

- **Title:** Identify the one host and name the document as its document authoring profile.
- **Frontmatter:** None. Begin with the standalone GFM title; put profile identity, own edition, and value declarations in the body. Governing source: Type-owned DOCUMENT-AUTHORING-PROFILE@host policy; no external publication metadata schema is selected.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State profile identity, own edition, and host scope before the initial declarations; resolve actor and authority references before their dependent interpretation; place limitations with or after the values they qualify.
- **Presentation:** Use a compact declaration table and repeated actor and assignment tables near the start, with concise prose for limits. Required semantic roles may share sections when every field, condition, and unresolved fact remains retrievable; do not require a separate chapter per role.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Host authoring profile (standalone) | The profile owns one H1 identifying its host and purpose. Profile ID, own edition, host scope, and declarations are body content, not inherited host-application metadata. | Use GFM tables and prose for the declared values and repeated actor and assignment entries; no native executable schema or parser is selected. The profile supplies only its applicable declared items to other documents. Resolve material conflicts before applying a value; these declarations do not grant execution permission. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Profile identity and host scope | Required | Identify the profile, its own edition, one stable host identifier, applicability and exclusions, accountable maintainer, and organization or assessed absence. Include the client element. Keep the profile's own edition independent of the specification's edition. Use the Declaration vocabulary for the named values. |
| Initial value declarations | Required | Place the Declaration vocabulary values near the beginning of the finished body, after enough identity and scope to select the correct host. Declare each applicable variable once, with a concrete value or a visible unresolved disposition. Include actor entries, applicable role assignments, and the agreed conventions; conditional fields state their applicability or an assessment reason. Preserve the names in the vocabulary so readers can resolve references without interpreting executable expressions. Values applied to a target document MUST NOT retain fill-in markers or consequential unresolved facts. |
| Actors, assignments, and authority | Required | Identify each distinct actor by stable nonsecret internal ID, declared name, and position or established organizational role. Resolve every role and maintainer reference to an actor. Assign the applicable author, issuer, maintainer, reviewer, approver, and exception-authority roles with explicit document or process applicability; identify unused roles instead of inventing assignments. One person may hold several roles by sharing one actor entry. For an issuing person, supply full name, position, internal ID, and actual mandate and limits; identify the decision rights of approvers and exception authorities. Preserve any real separation of duties; do not call a review independent when the same person authored it. |
| Value interpretation and limits | Required | Distinguish supplied facts, proposals, unknowns, and inapplicable fields. A generic role, account name, Git author, or skill author does not establish a person's identity or issuing mandate. Describe conflicting values and their resolution authority; an explicit task value cannot silently override a controlling obligation or mandate. The profile supplies authoring data, not execution permission or a replacement for a target document's selected specification. Source specification identity and edition, document ID and edition, scope, authorship events, approvals, effective dates, assessment results, and event references remain facts of each target document; conventions may define their representation but MUST NOT predeclare those facts. A target document receives only applicable declared items; do not require it to cite this profile or its edition, record its use, or include profile history. |
| Process or service responsibility references | Conditional when the declared authoring scope relies on an established process or system or service ownership assignment | Identify the relevant process or system or service by its established ID or usable reference and resolve its responsible actor. Keep these links limited to interpreting authoring responsibility; they are not an asset inventory, an incident chronology, proof of an executed action, or causal attribution. An actual event reference and event time belong to the document or record reporting that event, not to reusable host defaults. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Host and profile identity | Exactly one host ID, profile ID, profile edition, and applicability boundary in Profile identity and host scope. | Use stable nonsecret identifiers and an edition that identifies the profile's current content. Do not equate a host alias with a network address or infer applicability from file location. |
| Declared value | One value or explicit gap for every applicable Declaration vocabulary field in Initial value declarations. | A declared value is authoring data with identified scope and basis. Unknown, not yet decided, and not applicable differ; explain consequential gaps and never treat an empty field as a default. |
| Actor | One entry per distinct actor in Actors, assignments, and authority; one or more actors are needed for a profile. | An internal ID identifies one actor. Name and position identify an issuing person; an ID is not a secret or a government identity document. Contact and affiliation are conditional on actual need and disclosure permission. |
| Role assignment | One or more applicable assignments in Actors, assignments, and authority; zero assignments for an explicitly unused role. | Each role reference identifies an existing actor and an explicit scope; resolve conflicting overlapping assignments before use. Repeated actor references across roles are valid, but cannot establish independent review. |
| Mandate | One actual basis and applicable limits per issuer, approver, or exception-authority assignment in Actors, assignments, and authority. | A proposed authority remains proposed until its actual assignment is established. Naming a role or recording a document does not grant the represented authority. |
| Convention | One declared rule or explicit disposition per applicable convention in Initial value declarations. | Conventions may govern language, time and date representation, document IDs, local editions, review, classification, distribution, retention, and exceptions. Do not infer a legal retention duty, source-specification edition, or target-document decision from a formatting convention. |
| Responsibility reference | One per established process or system or service assignment covered by Process or service responsibility references; zero when that conditional role is inapplicable. | Bind the established context identifier, actor, and applicability. Missing event evidence cannot be supplied by the document author's identity or a reusable role assignment. |

Use the Declaration vocabulary as the field contract for the finished profile's initial variables and repeated items. Fill applicable declarations with established values; do not copy a blank form or specimen into a profile. The profile's own edition identifies its declared content. Any profile change records belong to the responsible process; applying declared items adds no recording duties to the profile or its consumers. No new parser, skill workflow, installation path, publication procedure, or universal retention or review interval is prescribed.

### Declaration vocabulary

The following vocabulary defines authoring data, not executable configuration or a blank production record. Put resolved declarations near the start of the finished profile. Semicolon-separated names identify separate variables; prefixed item groups repeat by their stated identity. Each variable or item has one controlling value within its applicability. Do not add a reusable target-document approval, effective date, observed result, or event identifier.

| Variable or item fields | Inclusion and value rule | Interpretation and source constraint |
|---|---|---|
| PROFILE_ID; PROFILE_EDITION | Required: one nonempty identifier and one unambiguous local edition for this profile. | Retain the profile ID and increment the profile's own edition when issuing a new edition of the same profile, independently of the specification's edition. These values identify the profile and are not additional content for documents using its items. |
| HOST_ID; APPLICABILITY | Required: one nonsecret host identifier and an explicit covered host, work context, document scope, and exclusions. | A file path, environment account, or current machine name alone is not an applicability decision. |
| EXTERNAL_CLIENT | Required to address for this profile's actual commissioning or receiving relationship. | Name an established external party and relationship, or state that this profile has no external client; do not make the profile's client a default for other documents. |
| ORGANIZATION; UNIT | Conditional on an established organizational relationship. | Use declared names; state assessed absence or inapplicability without inventing an organization. |
| MAINTAINER_ID | Required: one actor reference or an explicit assignment gap. | Resolve the maintainer to an existing actor; do not infer the assignment from an environment account. |
| ACTORS: ACTOR_ID; NAME; POSITION | One entry per actor; each applicable assignment resolves a nonempty ID, declared name, and position or established role. | The issuing person's name, position, and internal ID remain independently retrievable; one actor may fill several roles. |
| ACTORS: ORGANIZATION; CONTACT_REF | Conditional on actual affiliation or a needed established internal contact route. | Use only necessary authorized information, not credentials, private keys, government identity numbers, or inferred personal details. |
| ASSIGNMENTS: ROLE; ACTOR_ID; APPLICABILITY | One entry per applicable author, issuer, maintainer, reviewer, approver, or exception-authority assignment. | Use the stated role labels, an existing actor ID, and decidable scope; document unused roles and unresolved overlaps. |
| ASSIGNMENTS: AUTHORITY_BASIS; LIMITS | Basis required for issuer, approver, and exception authority; limits required to address for those assignments. | State the actual mandate and its scope, conditions, and expiry when established; an unknown material limit blocks dependent authority claims. |
| LANGUAGE; TIME_ZONE; DATE_FORMAT; TIMESTAMP_FORMAT | One agreed value or disposition per applicable representation convention. | Use an established language and time zone; timed facts retain offsets or time-zone context and actual precision. Do not guess the host time zone from the author's session. |
| DOCUMENT_ID_RULE; LOCAL_EDITION_RULE; DOCUMENT_REVIEW_RULE | One agreed rule or explicit disposition per applicable document-control convention. | Define identity uniqueness, revision meaning, and review triggers without predeclaring a particular target document's ID, edition, next review date, or approval. |
| CLASSIFICATION; DISTRIBUTION; RETENTION_RULE; EXCEPTION_RULE | One agreed rule or explicit disposition per applicable handling convention. | State the actual protection, audience, retention basis, and permitted exception boundaries; do not infer disclosure permission or a legal duty. |
| RESPONSIBILITY_LINKS: CONTEXT_REF; ACTOR_ID; APPLICABILITY | Conditional: one entry per in-scope process or system or service responsibility relied on by the profile. | Resolve the established context, responsible actor, and boundary; leave actual change and event attribution to their own evidence. |

## Quality criteria

- The profile identifies exactly one host, its applicability, profile ID and own edition, maintainer, and organizational or client dispositions without implying permission from its location.
- Applicable variables occur near the beginning, use the declared vocabulary, and resolve to concrete values or explicit gaps; values used for authoring contain no unfilled markers or consequential unknowns.
- Actor IDs are unique and role references resolve; each issuing person has retrievable name, position, internal ID and actual mandate with scope and limits. Multi-role assignments do not fabricate independent review.
- Material identity, authority, and convention declarations reflect established facts; gaps and conflicts expose their consequence and resolution route without fabricated facts.
- A target document receives only applicable declared items and retains its selected type contract; using the profile adds no profile citation, edition binding, use record, or profile history.
- Conditional process or service references identify their actual context and actor without becoming an inventory or asserting event execution or causal responsibility.
- A new edition retains the profile ID and increments the profile's own edition independently of the specification; the profile contains no change or use records and applying its items imposes none on consuming documents.
- Out-of-scope, unresolved, or conflicting declarations prevent the affected use, and the profile contains no secrets or unnecessary personal or infrastructure data.
