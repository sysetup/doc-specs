# SYSETUP document specifications

```console
   ____             __
  / __/_ _____ ___ / /___ _____ _/|
 _\ \/ // (_-</ -_) __/ // / _ > _<
/___/\_, /___/\__/\__/\_,_/ .__//
    /___/                /_/
> Systems development company.
```

[sysetup.com](https://sysetup.com/) · [Document catalog](INDEX.md)

## Overview

This collection provides **120 Markdown document specifications** across governance, processes, plans, specifications, control records, and evidence. Each specification defines a document's purpose, use boundary, content obligations, and quality criteria.

## Using this collection

This package guides agents that write final, project-specific Markdown documents. Select a document type by its purpose and use boundary in [INDEX.md](INDEX.md), the complete catalog of document types. Read the selected specification in full, obtain the required project facts and actual evidence from the supplied project data, write the document, and check its content and quality against that specification.

## Authoring conventions

- **Specification:** Instructions for authoring one document type, including its use boundary, content obligations, and quality criteria. Apply those instructions to the project's established facts and evidence when writing the finished document.
- **Format:** The representation of content, such as Markdown prose, a table, a diagram, or YAML frontmatter. A format alone does not define a document's purpose or required content.
- **Finished document:** A specific authored record that applies a specification to established project facts and evidence.
- **Required:** Include the stated content in every finished document of that type.
- **Conditional:** Include the stated content when the specification's explicit condition applies. If applicability cannot be established, resolve it or follow the specification's direction for that uncertainty.
- **Optional:** Include the content when it helps the document's purpose without obscuring required content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.

In specifications, **MUST** and **MUST NOT** state requirements or prohibitions. **SHOULD** states the normal choice; a justified case may depart from it. **MAY** grants an option. These words govern the authoring agent and its finished document. Do not invent facts, decisions, approvals, results, or references to satisfy a requirement; handle missing or inapplicable information as the selected specification directs.

## Output conventions

The finished document's body uses GitHub Flavored Markdown (GFM). Its specification determines the title, section roles and order, and suitable forms for its content. Check both the Markdown structure and the support for project claims in the supplied facts and actual evidence.

YAML frontmatter is a separate convention; it is not part of GFM. Each type specification states whether its finished document has frontmatter. When required, place a YAML 1.2-compatible mapping before the Markdown body, between opening and closing `---` lines, and use only the fields that specification defines under their stated conditions. Frontmatter fields must describe the finished document itself; subject-matter content belongs in the body. Quote string values when an unquoted value could be parsed as another type. When the specification says no frontmatter, begin with the Markdown body. Include metadata fields and document-control sections only as defined in the selected specification. Place the client or receiving-party element in the body identity or scope section under the conditions defined above.
