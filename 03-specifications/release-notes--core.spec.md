---
title: "Release notes specification"
description: >-
  Defines the authoring contract for recipient-facing release notes communicating the material changes, required user or operator actions, compatibility effects, known limitations, and unresolved items associated with one identified release. Connects recipient-visible facts to an underlying release record when present while keeping internal deployment execution logs, multi-release cumulative histories, internal engineering details, and unverified release or upgrade claims out of the recipient notice.
topics:
  - "release-notes"
  - "release-communication"
  - "compatibility-effects"
  - "recipient-actions"
  - "known-limits"
  - "change-notice"
use_when:
  - "A specific product or service release needs a concise notice informing recipients of changes, upgrade actions, compatibility, and limits."
  - "A release coordinator is authoring user-facing upgrade instructions and breaking-change warnings for one release."
  - "A reviewer is checking whether recipient-facing release notes expose required actions and unresolved limitations truthfully."
not_for:
  - "Maintaining a cumulative multi-release history plus pending unreleased work, which belongs in a cumulative changelog."
  - "Recording internal deployment actions, artifacts, and release authorization evidence, which belongs in a release record."
  - "Communicating vulnerability applicability and remediation across affected versions, which belongs in a recipient security advisory."
---

# Release notes specification

## Identity and selection

- **Specification ID:** `RELEASE-NOTES@core`.
- **Specification edition:** `1.0`.
- **Purpose:** State the changes in one release that a recipient must know.
- **Intended readers:** Recipients of that release, and the people who support them, who need its changes and their recipient effects.
- **Decision or action supported:** A recipient can tell what changed, what action the change requires, and which limits still apply.
- **Use when:** One release has changes a recipient must know before or while taking that release.
- **Scope boundaries:** Cover recipient-facing changes, actions, compatibility effects, and limits for one release.

## Authoring inputs and unresolved facts

Obtain the release identity the notes cover, the recipient audience, the changes those recipients must know, the action or compatibility effect of each change, and any known limit that changes how the release should be taken. Inspect an actual release-event record when one exists to establish the release identity and changes.

If a change, its recipient effect, or the release identity is unknown, say so. Do not invent a change, a fix, or a breaking effect. A commit identifier MAY support a change when the project actually uses it; it does not replace the recipient-facing statement.

## Finished-document contract

- **Title:** Identify the product or system and the release, and name the document as its release notes.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). Release identity belongs in the body. Governing source: Collection Semantic-Discovery Frontmatter contract (standard 3.0.0).
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the release before the changes. State recipient actions and known limits with or after the changes. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the product or system, the one release these notes cover, the recipients, and any actual release-event record cited. Include the client or receiving-party element from this contract when applicable. |
| Changes the recipient must know | Required | For each change the recipient must know, state what changed and why it matters to that recipient. If no such change is established, say so rather than filling the section with an unowned commit list. |
| Actions, compatibility, and known limits | Required | State the action a recipient must take, any compatibility or upgrade effect, and any known limit that changes how the release should be taken. An unknown effect stays unresolved. |
| Unresolved items | Conditional: a change or its recipient effect is not established | State the gap, its consequence for the recipient, and the next resolving action. Omit this section only when no such gap exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Release identity | One release per document. | Name the release the notes cover. Do not merge several releases into one unnoticed set. |
| Recipient change | Zero or more changes a recipient must know. | State the recipient-visible change and its effect. A commit list without that effect is not a change entry. |
| Required recipient action | Zero or more actions, each tied to a change or to the release as a whole. | State who should act and what they should do. Do not invent an action. |
| Compatibility or limit | Each material compatibility effect or known limit. | Separate a known limit from an unknown effect. |
| Release-record citation | Conditional when a release record exists. | Cite the actual record by identity and locator, linking it to the release covered by these notes. |

Use a list or table of changes with a recipient effect for each entry. Prose should explain a compatibility or upgrade consequence that a table would hide. Do not reproduce an empty change row.

## Quality criteria

- The notes cover one release and state the changes a recipient must know, or they state that no such change is established.
- Each stated change has a recipient effect. An unknown effect remains visible.
- The document invents no change, party, or release outcome.
