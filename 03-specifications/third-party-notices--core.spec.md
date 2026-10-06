# Distributed third-party notices specification

## Identity and selection

- **Specification ID:** `THIRD-PARTY-NOTICES@core`.
- **Purpose:** Assemble sourced third-party notices and attribution accompanying an identified distributed artifact.
- **Intended readers:** Distribution recipients, release maintainers, component stewards, and authorized intellectual-property reviewers.
- **Decision or action supported:** Locate faithfully preserved upstream notices and unresolved distribution obligations for the actual package.
- **Use when:** Distribution of third-party material has established notice or attribution obligations.
- **Scope boundaries:** Define distribution-scoped notice assembly and source traceability; exclude component metadata alone, novel license drafting, inferred redistribution rights, and legal-compliance certification.

## Authoring inputs and unresolved facts

Inspect the exact distributed artifact and included third-party versions, authoritative upstream license and notice text, source editions and permitted substitutions, actual distribution and attribution obligations, modifications where disclosure is required, composition evidence, authorized rights review, controlling notice placement, and packaging checks actually performed.

Expose unknown component version, upstream text, distribution scope, rights, attribution, or packaging basis with its consequence, resolving action, and assigned owner if known. Missing rights or mandatory notice facts block claiming the package is cleared for distribution; do not invent license clauses, copyright holders, dates, attribution, or permissions. Preserve authoritative text and escalate uncertain obligations for competent review.

## Finished-document contract

- **Title:** Identify the distributed artifact and version and name its third-party notices.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify distribution scope and provenance before component notices; put required modification or offer information with the affected notice, followed by placement checks and unresolved obligations. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Distribution identity and source basis | Required | Identify actual artifact, version or immutable package identity, distribution boundary, component evidence and notice-source editions, permitted audience, and client or receiving-party element. State the controlling notice files and their intended locations. |
| Component notices and attribution | Required | For each component with an applicable obligation, identify included version and origin and faithfully preserve required copyright, license, notice, and attribution text from inspected upstream sources. Record authorized substitutions without changing substantive legal wording. |
| Additional distribution obligations | Conditional when inspected source terms require modification notices, source availability information, written offers, or other accompanying statements | Provide required accompanying information only from the actual obligation and authorized arrangement, with affected component, source, period or scope, and usable location. Do not invent source-offer commitments or apply one component's obligations universally. |
| Assembly, packaging, and unresolved items | Required | Reconcile included components and applicable notices, identify native files or attachments preserving exact text, state placement and actual packaging-check status, and expose missing provenance, rights, text, or obligations with resolution routes. Authorship and a complete-looking list do not establish legal clearance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Distributed artifact | Exactly one artifact and version or explicitly bounded package set in Distribution identity and source basis. | Bind the obligation assessment to actual distributed contents, not every development dependency. |
| Notice-bearing component | One or more entries in Component notices and attribution. | Each has included identity, version, origin, and source terms; if no applicable notice obligation exists, use a reasoned distribution assessment rather than this populated notice contract. |
| Upstream notice text | One or more required text blocks or exact attachments per applicable component in Component notices and attribution. | Preserve text and authorized substitutions faithfully; a license identifier or link alone is insufficient when text must accompany distribution. |
| Additional obligation | Zero or more in Additional distribution obligations. | Applicability comes from inspected source terms; unknown rights or offers require review and do not confer permission. |
| Packaging and reconciliation basis | Exactly one account in Assembly, packaging, and unresolved items. | Name actual artifact, notice locations, controlling native text, included-component coverage, checks and gaps; a narrative cannot substitute for absent packaged notices. |

Use GFM for distribution context, component-to-source mapping, and unresolved items. Preserve verbatim upstream content in exact native notice files or attachments when its whitespace or syntax cannot be faithfully represented in GFM; explicitly identify that controlling representation and verify package placement. Do not rewrite upstream legal text to fit a prose summary.

## Quality criteria

- Artifact, distribution scope, actual included components, and source editions define the obligation assessment.
- Each applicable component has sourced attribution and faithfully retained required text, with only authorized substitutions.
- Additional statements and offers reflect actual applicable obligations and authorized arrangements rather than invented rights.
- Reconciliation and package placement are checked or explicit gaps; native text remains controlling and legal clearance is not inferred.
