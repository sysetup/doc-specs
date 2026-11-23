---
title: "{{CATALOG_NAME}} specification"
description: >-
  {{SEMANTIC_DISCOVERY_DESCRIPTION_60_TO_140_WORDS_RULE_13_COMPLIANT}}
topics:
  - "{{TOPIC_1}}"
  - "{{TOPIC_2}}"
  - "{{TOPIC_3}}"
use_when:
  - "{{NEUTRAL_USE_WHEN_CONDITION_1}}"
  - "{{NEUTRAL_USE_WHEN_CONDITION_2}}"
not_for:
  - "{{GROUNDED_EXCLUSION_OR_OMIT_KEY_WHEN_EMPTY}}"
---

# {{CATALOG_NAME}} specification

## Identity and selection

- **Specification ID:** `{{TYPE}}@{{VARIANT}}`.
- **Specification edition:** `{{EDITION}}`.
- **Purpose:** {{PURPOSE}}
- **Intended readers:** {{READERS}}
- **Decision or action supported:** {{DECISION}}
- **Use when:** {{USE_WHEN}}
- **Scope boundaries:** {{SCOPE}}

## Authoring inputs and unresolved facts

{{INPUTS}}

{{UNRESOLVED}}

## Finished-document contract

- **Title:** {{FINISHED_TITLE}}
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). {{FRONTMATTER_BODY_BOUNDARY_RULE}} Governing source: {{FRONTMATTER_SOURCE}}
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** {{FINISHED_ORDER}}
- **Presentation:** {{PRESENTATION}}

{{METADATA_FIELD_TABLE_WHEN_TYPE_OVERRIDES_EXIST}}

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| {{PROJECTION_NAME}} ({{PROJECTION_KIND}}) | {{PROJECTION_TITLE}} {{PROJECTION_METADATA}} | {{PROJECTION_SYNTAX}} {{PROJECTION_AUTHORITY}} |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| {{ROLE}} | {{RENDERED_STATUS}} | {{OBLIGATION}} |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| {{ELEMENT}} | {{MEANING_AND_CARDINALITY}} | {{CONSTRAINT}} |

{{FORMS}}

{{SUPPORTING_H3_AND_LITERAL_CONTENT_BLOCKS_WHEN_NONEMPTY}}

## Quality criteria

- {{CRITERION_TEXT}}
