---
title: "Product guide specification"
description: >-
  Defines the authoring contract for recipient-facing product guides explaining how to install, configure, operate, and recover a delivered product within stated conditions and version boundaries. Covers product scope and applicability, installation prerequisites and steps, configuration settings and effects, ordinary user tasks with expected results, operational limits, troubleshooting or failure recovery, and explicit disclosure of unresolved facts so recipients use the delivered product safely and accurately.
topics:
  - "specifications"
  - "product-and-discovery"
  - "product-guide"
  - "installation-guide"
  - "configuration-guide"
  - "user-manual"
  - "recipient-documentation"
  - "product-usage"
use_when:
  - "A delivered product or tool needs recipient-facing instructions covering installation, configuration, everyday use, and recovery limits."
  - "An author is writing a user manual or product operations guide aligned with actual delivered product behavior."
  - "A reviewer is checking whether installation steps, settings, expected results, and boundaries reflect verified behavior without overclaiming."
not_for:
  - "Concise symbol, API, CLI flag, or schema lookup without task walkthroughs, which belongs in a technical lookup reference."
  - "Hands-on pedagogical exercises with learner checkpoints and cleanup, which belong in a learning tutorial."
  - "Internal service recovery commands for operators managing a specific deployment target, which belong in an operational runbook."
  - "Disclosing an AI model or system's training provenance, intended and out-of-scope uses, known biases, evaluation citations, and oversight limits, which belongs in an AI model or system card."
---

# Product guide specification

## Identity and selection

- **Specification ID:** `PRODUCT-GUIDE@core`.
- **Purpose:** Explain how to install, configure, and use the delivered product.
- **Intended readers:** The people who install, configure, or use that product, and the role that keeps the guide aligned with the delivered behavior.
- **Decision or action supported:** A reader can install, configure, and use the product within the conditions the guide actually states.
- **Use when:** A delivered product needs recipient-facing instructions for installation, configuration, and use.
- **Scope boundaries:** Cover recipient-facing installation, configuration, and use for the stated product and version.

## Authoring inputs and unresolved facts

Obtain the product identity and delivered version or version range, the audience, the supported environment, the installation path, the configuration the user must set, the ordinary use the product provides, and the limits or recovery a user needs. Inspect the product's actual behavior or an established description of it.

If a step, setting, supported environment, or limit is unknown, say so and do not invent it. If the product has no installation, or no user configuration, state that with a scope reason and omit the empty procedure. Label an unreleased or proposed behavior as proposed. Describe steps and expected outcomes without claiming that a reader has performed them.

## Finished-document contract

- **Title:** Identify the product and name the document as its product guide.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Product identity and the guide's covered version belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the product and audience before installation, configuration, and use. State limits and unresolved items after the procedures. Heading wording may vary.
- **Presentation:** Use concise recipient-facing prose, task lists, or compact reference tables proportional to the product or release scope. Required roles may share sections while keeping supported versions, prerequisites, expected outcomes, routing paths, and known limits immediately scannable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Product guide (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one subject-specific H1. Subject identity, applicable version or maturity, scope boundaries, and ownership remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, diagrams, or code blocks grounded in controlling project sources and inspected editions. External native models, schemas, or artifacts remain authoritative for their own formats; source or baseline changes require reconciliation before retaining current applicability. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the product, the version or version range this guide covers, the audience, the supported environment, and what the guide does not cover. Include the client or receiving-party element from this contract when applicable. |
| Installation | Conditional when the product is installed by the reader | Give the prerequisites, the installation sequence, and the check that shows installation completed. If the product is not installed by the reader, omit the procedure and state that reason in identity and scope. |
| Configuration | Conditional when the reader must set product configuration | State each setting the reader must choose, the effect of the choice, and the value or rule when one is established. An unknown setting stays unresolved. Do not invent a default and present it as required. |
| Use | Required | Explain the ordinary use the product provides, the inputs the reader supplies, the result the reader should see, and the conditions under which that use applies. |
| Limits, recovery, and unresolved facts | Required | State material limits, the user-visible recovery or failure behavior that is established, and any unknown step, setting, or environment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Product and version | One product and the version or range this guide covers. | Do not present the guide as current for an unstated version. A proposed version is labeled proposed. |
| Reader task | One or more use paths; installation and configuration only when they apply. | Keep each path something the product's reader does. |
| Setting | Zero or more settings the reader must set. | State the name, the effect, and the established value or choice. An unknown value remains unknown. |
| Expected user result | One result for each stated use path. | Describe the expected observable outcome of the path. |
| Limit or failure | Each material limit or user-visible failure the guide relies on. | State what the reader can do. Do not invent a recovery the product does not provide. |

Use ordered steps for installation and for a use path whose sequence matters. Use a table for settings when several must be compared. Prose should explain what the product does and when a path does not apply.

## Quality criteria

- The guide tells a reader how to install, configure, and use the stated product version, or it states which of those paths does not apply.
- Steps and explanations address the product's recipients and stated use paths.
- Unknown steps, settings, and environments stay visible. The guide invents no behavior, party, or completed installation.
