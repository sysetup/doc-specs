# SYSETUP document specifications

```console
   ____             __
  / __/_ _____ ___ / /___ _____ _/|
 _\ \/ // (_-</ -_) __/ // / _ > _<
/___/\_, /___/\__/\__/\_,_/ .__//
    /___/                /_/
> Systems development company.
```

[sysetup.com](https://sysetup.com/) · [document catalog](INDEX.md)

## Overview

This collection provides **143 Markdown document specifications** across governance, processes, plans, specifications, control records, and evidence. Each specification defines a document's purpose, use boundary, content obligations, and quality criteria.

Current collection release: [2026-10-06](CHANGELOG.md#release-2026-10-06). It includes all 143 catalog specifications, the authoring standard 2.0.0, both authoring templates, and the family registry. The authoring standard is released, adopted, and effective from this collection release.

The collection helps engineers, project owners, operators, and reviewers develop documentation grounded in their project's facts and evidence. It supports manual and automated authoring.

A specification describes what a document needs to accomplish and contain. The finished document is the project-specific result of applying that specification. The collection does not supply project facts, completed records, or operational authorization.

## Repository organization

| Directory | Contents |
|---|---|
| `00-governance/` | Policies, an internal standard, and an engineering guide. |
| `01-processes/` | Lifecycle processes, runbooks, playbooks, procedures, and work instructions. |
| `02-plans/` | Engineering, operations, assurance, continuity, and maintenance plans. |
| `03-specifications/` | Requirements, architecture, design, interfaces, test specifications, and product documentation. |
| `04-control/` | Registers, matrices, requests, decisions, and other control records. |
| `05-evidence/` | Reviews, execution records, assessment evidence, reports, releases, and handoffs. |
| `authoring/` | Family registry, structured request template, and specification template for maintaining the collection. |

The [document catalog](INDEX.md) lists each type's purpose, use boundary, and specification. The numbered directories contain authoring specifications rather than completed documents. The table above describes current contents; [authoring/families.json](authoring/families.json) alone defines family responsibilities, boundaries, and order for classification, request validation, placement, and counting. The six existing families remain defaults; extension requires a sourced mission and the controlled procedure in CONTRIBUTING.md.

[llms.txt](llms.txt) provides an entrypoint for automated readers. [CHANGELOG.md](CHANGELOG.md) records releases and pending changes. The collection is distributed under the [MIT License](LICENSE).

## Adding document specifications

[CONTRIBUTING.md](CONTRIBUTING.md), released version 2.0.0, requires mission and source discovery before classification, task-to-content-to-case coverage, type-specific frontmatter and projection rules, and representative finished-instance evaluation before deterministic composition. Use its [structured request template](authoring/request.template.json) and [specification template](authoring/specification.template.md) after reading the method. Required information may share proportionate paragraphs, lists, or sections.

The `authoring/` directory contains those templates and the family registry, outside the catalog count. No installed renderer or validator is supplied. Version 2.0.0 changes the request interface for new contributions and explicitly requested revisions; existing specifications and historical 1.0.0 requests retain their original contracts. Do not recompose historical evidence with current rules or retrospectively migrate unaffected files.

## Using the collection

1. Find the document type in [INDEX.md](INDEX.md) that matches the purpose and scope of your work.
2. Read its specification to understand the required inputs, document structure, content obligations, and quality criteria.
3. Prepare the document using established project facts and actual evidence, then review its content and declared reader tasks. Apply only its defined metadata and projection policy; preserve native authority. Missing information remains visible according to that specification. Do not infer mission fitness, execution, or human usability from a structural check.

For example, [software requirements](03-specifications/software-requirements--core.spec.md) describe obligations allocated to a software item, while [software design](03-specifications/software-design-description--software.spec.md) describes its realization. Selection depends on the document's purpose and use boundary, rather than its filename alone.

Finished documents belong with their owning project or in its authorized documentation location. This repository provides the specifications used to author them.

## Reading a specification

- **Required** content appears in every document of that type.
- **Conditional** content applies when the stated condition is met.
- **Optional** content can help explain the subject without obscuring required content.
- **MUST** and **MUST NOT** express requirements and prohibitions; **SHOULD** expresses the normal choice with justified departures; **MAY** expresses an option.

The document body uses GitHub Flavored Markdown. YAML frontmatter is a separate convention whose applicability and fields are defined by the selected specification. A format, such as a table or diagram, does not itself determine a document's purpose or content obligations.

## Documentation scope

This repository maintains reusable document specifications, their catalog, and the authoring resources listed above. It can be read directly from a checkout; it supplies no installation scripts, renderer, or automated validator.

Finished project, host, and service documentation belongs in the owning project's or environment's authorized documentation location. Use that owner's established review and publication workflow for changes. The collection prescribes neither fixed paths under a home directory nor a separate directory for proposed documentation.

The owning environment supplies operational agent instructions and determines how its harness loads them. [CONTRIBUTING.md](CONTRIBUTING.md) governs maintenance of this specification library; operational authorization comes from the responsible project or environment.
