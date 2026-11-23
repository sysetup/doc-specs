---
title: "Cumulative changelog specification"
description: >-
  Defines the authoring contract for cumulative changelogs maintaining a meaningful, human-readable chronological history of notable changes across established releases alongside a clearly separated pending unreleased section for one identified subject. Covers history boundaries, categorized change entries, handling of exceptional history such as yanked releases or backports, supporting references, and explicit coverage limits while excluding raw commit dumps, single-release recipient notices, and release execution or authorization evidence.
topics:
  - "control-records"
  - "change-and-release"
  - "cumulative-changelog"
  - "version-history"
  - "unreleased-changes"
  - "change-categorization"
  - "release-history"
  - "software-maintenance"
use_when:
  - "A project, product, or corpus maintains a cumulative version-by-version history plus pending unreleased changes."
  - "A maintainer is categorizing notable additions, changes, removals, fixes, or exceptional release history across versions."
  - "A reviewer is verifying that pending work stays clearly separated from established releases and avoids raw commit dumps."
not_for:
  - "Writing a one-release upgrade notice focused solely on recipient actions, which belongs in release notes."
  - "Preserving accountable deployment execution, artifacts, and channel evidence for one release, which belongs in a release record."
  - "Authoring a repository entrypoint or setup overview, which belongs in a repository overview."
---

# Cumulative changelog specification

## Identity and selection

- **Specification ID:** `CHANGELOG@core`.
- **Purpose:** Maintain a meaningful history of changes across established versions and separately identified pending work.
- **Intended readers:** Product recipients, developers, maintainers, release coordinators, and readers comparing versions.
- **Decision or action supported:** Identify what changed across versions, what remains pending, and which material effects need further guidance.
- **Use when:** A project, product, or bounded component maintains cumulative change history.
- **Scope boundaries:** Maintain versioned history and pending changes for one identified subject; exclude raw commit dumps, one-release recipient notices, and release authorization or execution evidence.

## Authoring inputs and unresolved facts

Inspect the subject and covered history boundary, actual change sources, release identities and status, known release dates and their precision, pending changes, established versioning policy, meaningful recipient or developer effects, exceptional releases, and real release, tag, comparison, issue, or evidence references.

Expose unknown version, date, consequence, release state, or historical coverage with its effect, resolving action, and assigned owner if known. Preserve established history and label imported coverage gaps; missing dates do not become invented release dates. Pending entries have no published date. Do not invent changes, fixes, versions, withdrawn status, or release outcomes.

## Finished-document contract

- **Title:** Begin with the GFM H1 Changelog and a short subject and coverage introduction.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify subject and history boundary first; put pending changes before established releases, list established releases most recent first within explicitly scoped release lines, and put exception or coverage notes after the affected entries. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Cumulative changelog (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Subject and history boundary | Required | Identify subject, audience, included components or release lines, history cutoff or import boundary, exclusions, established versioning policy or its absence, and the client or receiving-party element when applicable. State explicitly when no established releases or pending changes exist. |
| Pending changes | Conditional when pending entries exist or the project intentionally retains an Unreleased section | Use an Unreleased heading and explain meaningful pending changes and consequences. Keep intentionally empty pending sections distinguishable from unknown work, omit empty change categories, and assign no published release date. |
| Established release history | Conditional when one or more established releases exist in the covered history | Give each release its distinct identity, status, known date or date gap, and meaningful change entries. Use applicable Added, Changed, Deprecated, Removed, Fixed, and Security categories, omitting empty ones. Show material breaking effects and migration or advisory links when established; order recent releases first. |
| Exceptional history | Conditional when the covered history includes prereleases, withdrawn releases, corrections, or incomplete imported history | Identify exceptional status and its basis, preserve withdrawn releases as history, distinguish prerelease identity from stable release, and record material historical corrections or incomplete imports without erasing prior release facts. |
| Sources and coverage limits | Required | Bind material release and change claims to real supporting project sources through usable references or concise source notes. State unresolved dates, consequences, missing periods, and version-policy gaps, or their assessed absence. An entry is historical communication rather than proof of successful release or deployment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| History subject | Exactly one project, product, or explicitly bounded component set in Subject and history boundary. | Define release-line scope where chronology differs; do not merge unrelated version namespaces without labeling them. |
| Pending section | Zero or one Unreleased section in Pending changes. | Include under its condition; no release date is assigned and no pending entry is silently reported as published. |
| Release section | One per established release in Established release history; zero when none exist. | Use established version identity and status, and date when known; preserve imported uncertainty and distinct release lines. |
| Change entry and category | Zero or more meaningful entries per pending or release section. | Explain change and consequence; use only applicable declared categories, with no empty categories or unexplained commit-only entries. |
| Exceptional-history item | Zero or more in Exceptional history. | Identify source, affected version, status or correction, and coverage consequence; withdrawal preserves rather than deletes the release record. |
| Supporting reference | One or more usable sources for material history claims in Sources and coverage limits; zero only when no changes or releases are established. | Links and identifiers support explanation rather than replace it; a release tag or entry alone does not establish authorization or deployment. |

Use a short introduction, an optional Unreleased heading under its stated condition, version headings, and concise grouped change bullets. The category and history convention is compatible with [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/) without imposing Semantic Versioning. When publishing an established version's entries, preserve older sections and remaining pending work; validate source identities, dates, chronology, and references.

## Quality criteria

- Subject, version policy or gap, release-line scope, and historical coverage are explicit without forcing an unstated versioning scheme.
- Pending entries and intentionally retained empty Unreleased sections are distinct from published releases and carry no published date.
- Established releases retain distinct identities and sourced dates or gaps, recent-first ordering, meaningful consequences, and applicable nonempty categories.
- Prereleases, withdrawals, corrections, and incomplete imports retain their source and history rather than deleting inconvenient entries.
- Sources resolve and missing coverage remains visible; history maintenance invents neither release authority nor successful deployment.
