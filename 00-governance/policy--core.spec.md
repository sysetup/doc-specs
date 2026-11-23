---
title: "General policy specification"
description: >-
  Defines the authoring contract for general organizational or project policies setting authorized, mandatory, high-level direction outside specialized governance subjects. Requires explicit identification of issuing authority, policy ownership, applicability boundaries, issuance state and effective date, addressee-bound mandatory directives, accountability and conflict escalation, exception allowance or prohibition rules, and review cadence. Keeps policy text focused on high-level duties, decision rights, and outcomes without drifting into technical thresholds or detailed operational procedures.
topics:
  - "governance"
  - "quality-assurance"
  - "general-policy"
  - "organizational-governance"
  - "mandatory-directives"
  - "decision-rights"
  - "exception-governance"
  - "accountability"
use_when:
  - "An issuing authority needs to establish broadly applicable mandatory duties and decision rights for a general subject."
  - "An author is drafting an organizational or project policy outside configuration, cybersecurity, engineering, quality, or risk domains."
  - "A reviewer is checking whether a general policy separates proposed drafts from effective directives and defines real exception authority."
not_for:
  - "Specialized configuration, cybersecurity, engineering, quality, or risk management policies, which have dedicated policy specifications."
  - "Technical or practice criteria requiring detailed assessable checks, which belong in an internal standard."
  - "Nonbinding recommendations, practitioner options, or operational step-by-step procedures."
---

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

- **Title:** Name the policy subject and identify the document as a policy; a generic title such as "General Policy" alone is insufficient.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Policy authority and applicability are substantive content in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Present authority and scope before directives, and directives before exception and maintenance rules. Headings may use project wording if their semantic roles remain clear.
- **Presentation:** Scale structure to organizational scope using concise prose, numbered directives, and focused tables where authority or exceptions benefit from comparison. Required roles may share sections while keeping issuing authority, applicability, directives, and exception rules independently retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| General policy (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one subject-specific H1. Authority, applicability, issuance state, and ownership stay in the body, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, lists, or tables. Bind criteria, rationales, and references to actual organizational authorities and source editions; changes to governing mandates or scope require review before retaining active status. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Authority and applicability | Required | Identify the actual issuing authority or mark it as proposed; identify the policy owner (or inherit an explicit default maintainer declared at the corpus/catalog level when not overridden per document), controlled edition or other unambiguous version (which may be satisfied by a unified corpus version in `CHANGELOG.md` plus Git revision), issuance state, subject, affected people or functions, boundaries, exclusions, and effective date only when established by the proper authority. Distinguish authorization from the date a policy takes effect. |
| Purpose and mandatory direction | Required | Explain the desired outcome and state one or more clear, mandatory directives. Make the addressee and obligation discernible; group related directives without repeating them. Give rationale where it clarifies intent or a non-obvious boundary. Where a directive requires subsequent work, state that duty and its triggering condition explicitly. |
| Accountability and application | Required | State who must apply the directives, who interprets or oversees them, and how conflicts in obligations or decision rights are escalated or resolved. State the application conditions and decision bounds needed by each responsible role. |
| Exceptions | Required | State whether exceptions are allowed. If allowed, specify who may decide, the conditions and evidence for a request, the record required for the actual decision and any expiry or review, and what applies while a request is pending. If prohibited, state that rule and the route for raising a conflict. |
| Review and change | Required | Give a review cadence or concrete triggers, the role or authority for changes, and how approved changes are communicated and made effective. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Issuing authority | One identified body or delegated role with authority to issue this policy. | A draft may name a proposed authority, clearly labeled as such; it is not an issued policy. |
| Applicability | One explicit statement of the covered subject, people/functions, and organizational, project, system, or lifecycle boundaries that matter. | State material exclusions and avoid silently extending the mandate. |
| Issuance state and effective date | One truthful state; an effective date is conditional on a real effective-date decision. | Use the project's control vocabulary, but distinguish proposed, authorized but not yet effective, effective, and withdrawn or superseded states. Tie the stated version, authorization, and effective date to established issuance decisions. |
| Directive | One or more separately identifiable obligations. | Give each directive a stable local label or number and a clear addressee, mandatory action or constraint, and applicable condition. Keep the obligation at the level of high-level duties, decision rights, and outcomes. |
| Policy owner | One accountable role for maintenance and interpretation routing (which may inherit an explicit corpus/catalog default when recorded in the root catalog and not overridden). | Do not confuse this role with the issuing authority unless the project actually assigns both to the same body. |
| Exception rule | One rule covering allowance or prohibition. | When exceptions are permitted, define decision authority and decision bounds; a request never grants its own exception. Require an explicit decision and a record of its scope, conditions, and expiry or review rule. |
| Project decision or commitment reference | Zero or more references to supplied project decisions or commitments that explain a directive. | State the relevant project fact explicitly and identify its actual record, version, and locator when needed. |

Use concise prose for intent and application. Numbered directives or a compact table may help readers locate obligations; a table MUST NOT turn policy into empty field rows. A short decision flow may clarify the exception route when it branches. Do not add a document-control table, signature block, or checklist unless the project requires it.

## Quality criteria

- Each directive has an identifiable addressee and can be applied within the stated scope; obligations do not contradict one another or the exception rule.
- Readers can tell whether the text is proposed, authorized but awaiting effect, effective, withdrawn, or superseded, and which edition applies.
- Directives state mandatory high-level duties, decision rights, and outcomes; keep detailed technical thresholds and operational steps outside their scope.
- Exception and change authorities are real and consistent with the issuing mandate. Project references support the facts they identify; authorization and effective dates have an established decision basis.
