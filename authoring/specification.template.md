# {{CATALOG_NAME}} specification

## Identity and selection

- **Specification ID:** `{{TYPE}}@{{VARIANT}}`.
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
- **Frontmatter:** {{RENDERED_POLICY_PREFIX}}{{FRONTMATTER_RULE}} Governing source: {{FRONTMATTER_SOURCE}}
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** {{FINISHED_ORDER}}
- **Presentation:** {{PRESENTATION}}

{{METADATA_FIELD_TABLE_WHEN_FIELDS_NONEMPTY}}

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| {{PROJECTION_NAME}} ({{PROJECTION_KIND}}) | {{PROJECTION_TITLE}} {{PROJECTION_METADATA}} | {{PROJECTION_SYNTAX}} {{PROJECTION_AUTHORITY}} |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| {{ROLE}} | {{RENDERED_STATUS}} | {{OBLIGATION}} |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| {{ELEMENT}} | {{MEANING_AND_CARDINALITY}} | {{CONSTRAINT}} |

{{FORMS}}

{{SUPPORTING_H3_AND_LITERAL_CONTENT_BLOCKS_WHEN_NONEMPTY}}

## Quality criteria

- {{CRITERION_TEXT}}
