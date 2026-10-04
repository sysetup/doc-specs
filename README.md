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

This collection provides **120 Markdown document specifications** across governance, processes, plans, specifications, control records, and evidence. Each specification defines a document's purpose, use boundary, content obligations, and quality criteria.

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

The [document catalog](INDEX.md) lists each type's purpose, use boundary, and specification. The numbered directories contain authoring specifications rather than completed documents of those types.

## Using the collection

1. Find the document type in [INDEX.md](INDEX.md) that matches the purpose and scope of your work.
2. Read its specification to understand the required inputs, document structure, content obligations, and quality criteria.
3. Prepare the document using established project facts and actual evidence, then review it against the specification. Missing information remains visible according to that specification.

For example, [software requirements](03-specifications/software-requirements--core.spec.md) describe obligations allocated to a software item, while [software design](03-specifications/software-design-description--software.spec.md) describes its realization. Selection depends on the document's purpose and use boundary, rather than its filename alone.

Finished documents belong with their owning project or in its authorized documentation location. This repository provides the specifications used to author them.

## Reading a specification

- **Required** content appears in every document of that type.
- **Conditional** content applies when the stated condition is met.
- **Optional** content can help explain the subject without obscuring required content.
- **MUST** and **MUST NOT** express requirements and prohibitions; **SHOULD** expresses the normal choice with justified departures; **MAY** expresses an option.

The document body uses GitHub Flavored Markdown. YAML frontmatter is a separate convention whose applicability and fields are defined by the selected specification. A format, such as a table or diagram, does not itself determine a document's purpose or content obligations.

## Operational documentation architecture

The collection can participate in an environment that separates three documentation roles:

| Role | Responsibility |
|---|---|
| Document specifications | Authoring contracts, read-only for consumers. This repository is their maintained source. |
| Current operations documentation | Published guidance describing the host and its shared services. |
| Proposed operations documentation | Pending additions and changes awaiting publication by the designated responsible entity. |

`doc-operations/` and `doc-operations-update/` are representative directories in this repository. Each contains only an empty `.gitkeep` file so Git preserves the directory. They contain no current guidance or pending proposals and are not active operational stores.

Actual documentation roots are configured by the adopting environment. One installation convention places the three trees at `$HOME/.agents/doc-specs/`, `$HOME/.agents/doc-operations/`, and `$HOME/.agents/doc-operations-update/` as siblings. Using the specifications independently does not require installing the operational trees.

Project documentation stays with its owning project. Host-wide documentation changes are prepared in the configured proposal tree and remain pending until the designated responsible entity publishes them. This repository does not install those trees or publish operational changes.

[AGENTS.md](AGENTS.md) provides the production instructions for using the specifications and managing documentation. The host's agent harness determines where the file is installed and how it is loaded; it contains no installation automation.
