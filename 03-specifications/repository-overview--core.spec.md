---
title: "Repository overview specification"
description: >-
  Defines the authoring contract for concise development repository overviews providing prospective users, contributors, maintainers, integrators, and automated readers with an accurate entrypoint to the codebase and its authoritative documentation. Covers repository purpose, audience, maturity state, audience-specific starting routes, repository layout and documentation navigation maps, direct setup examples, collaboration and support routes, and explicit limits while excluding full product manuals, contributor rulebooks, and unsupported maturity claims.
topics:
  - "repository-overview"
  - "documentation-entrypoint"
  - "repository-navigation"
  - "quickstart"
  - "maturity-state"
  - "collaboration-routes"
use_when:
  - "A development repository needs a clear top-level overview guiding users, contributors, and automated readers to authoritative resources."
  - "A maintainer is documenting repository scope, maturity state, directory layout, setup examples, and support entrypoints."
  - "A reviewer is checking whether a repository overview stays concise and avoids unsupported maturity claims or installation authorization."
not_for:
  - "Comprehensive installation, configuration, and user task manuals for a delivered product, which belong in a product guide."
  - "Exhaustive API, CLI, or configuration lookup tables, which belong in a technical lookup reference."
  - "Detailed help-desk routing and security disclosure channels alone, which belong in a support and request-routing guide."
---

# Repository overview specification

## Identity and selection

- **Specification ID:** `REPOSITORY-OVERVIEW@core`.
- **Specification edition:** `1.0`.
- **Purpose:** Provide a concise entrypoint to a development repository and its authoritative documentation.
- **Intended readers:** Prospective users, contributors, maintainers, integrators, and automated readers discovering the repository.
- **Decision or action supported:** Identify the repository's purpose, maturity, starting route, and actual collaboration and support resources.
- **Use when:** A development repository needs an overview such as its README.
- **Scope boundaries:** Describe repository entry and navigation; exclude delivered-product task manuals, detailed contributor rules, unsupported maturity claims, and installation authorization.

## Authoring inputs and unresolved facts

Inspect the repository purpose, audiences, actual contents and layout, maturity and support statements, supported starting path and prerequisites, canonical project documentation, and real contribution, support, security, release, and license resources.

Expose unknown setup, platform support, maturity, resource, or license with its consequence and resolving action; name only assigned owners. A missing badge or document is not a failing product check, and an existing badge is not evidence beyond its actual target. Do not invent commands, channels, licensing rights, or working setup.

## Finished-document contract

- **Title:** Identify the repository or project as the H1; a README filename is permitted but not required.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract (standard 3.0.0).
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Explain purpose and audience before starting routes; present layout before documentation and collaboration navigation; place material limits and upkeep last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Purpose, audience, and state | Required | Identify the repository, problem or capability, intended audiences, actual maturity or proposal state, scope exclusions, and the client or receiving-party element when applicable. |
| Starting route | Required | Give the supported first action and prerequisites for each relevant audience, linking an actual maintained setup or use guide when available. If direct quick-start commands are included, verify them against the stated revision and distinguish expected outcomes from performed checks. State unsupported or unknown paths. |
| Layout and documentation map | Required | Describe material repository directories or components and link actual canonical requirements, architecture, design, reference, guides, or project records that help navigation. Omit invented or irrelevant sections and distinguish source documents from generated views. |
| Collaboration and recipient routes | Required | Point to established contribution, support, security-reporting, release-history, and license resources when applicable; state unavailable or unresolved routes. Binding obligations remain with their actual authority, and sensitive reports use only established private channels. |
| Limits and upkeep | Required | State material environment, maturity, compatibility, or documentation limitations, ownership or assignment gap, and update triggers from layout, setup, support, or release changes. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Repository scope | Exactly one repository or explicitly bounded repository set in Purpose, audience, and state. | Identify actual subject and maturity; a future capability is not delivered behavior. |
| Audience entry route | One or more in Starting route. | Each identifies prerequisites, supported revision or range, first action, and actual guide or explicit gap. |
| Navigation target | Zero or more in Layout and documentation map and Collaboration and recipient routes. | Each is an actual accessible target with the correct relative or published location; a generated view identifies its authoritative source. |
| Direct setup example | Zero or more in Starting route. | Use verified applicable commands and placeholders for sensitive inputs; examples do not authorize installation or production changes. |
| Status and maintenance claim | One account in Limits and upkeep. | State evidence for material claims and update ownership; badges and authorship do not establish approval, support, or compliance. |

Use concise prose, a short starting sequence, and a small linked documentation list or layout table. Prefer canonical guides over copying long installation or product instructions. The overview controls repository entry and navigation; linked source documents retain their detailed obligations.

## Quality criteria

- Purpose, audiences, maturity, scope, and starting routes are truthful and appropriate to the actual repository.
- Layout and linked resources exist, identify controlling sources, and use correct relative or published paths.
- Direct examples are applicable and checked or explicitly limited; no unsupported setup or authorization claim appears.
- Collaboration, license, security, support, and update information reflect real arrangements and visible gaps.
