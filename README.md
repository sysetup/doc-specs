# SYSETUP document specifications

```console
   ____             __
  / __/_ _____ ___ / /___ _____ _/|
 _\ \/ // (_-</ -_) __/ // / _ > _<
/___/\_, /___/\__/\__/\_,_/ .__//
    /___/                /_/
> Systems development company.
```

[sysetup.com](https://sysetup.com/) · [document catalog](INDEX.csv)

## Overview

This collection provides **144 Markdown document specifications** across governance, processes, plans, specifications, control records, and evidence. Each specification carries standardized 5-key Semantic-Discovery YAML frontmatter and defines a document's purpose, use boundary, content obligations, mandatory frontmatter contract, and quality criteria.

The latest declared collection release, [2026-11-23](CHANGELOG.md#release-2026-11-23), includes all 144 specifications upgraded to authoring standard `3.0.0`, the compact RFC 4180 discovery catalog [INDEX.csv](INDEX.csv), both authoring templates, and the family registry. Authoring standard `3.0.0` was adopted and took effect with that release.

The collection helps engineers, project owners, operators, reviewers, and automated agents develop documentation grounded in their project's facts and evidence. It supports both manual authoring and automated compilation workflows.

A specification describes what a document needs to accomplish and contain. The finished document is the project-specific result of applying that specification. The collection does not supply project facts, completed records, or operational authorization.

## Repository organization

| Directory | Contents |
| --- | --- |
| `00-governance/` | Policies, an internal standard, and an engineering guide. |
| `01-processes/` | Lifecycle processes, runbooks, playbooks, procedures, and work instructions. |
| `02-plans/` | Engineering, operations, assurance, continuity, and maintenance plans. |
| `03-specifications/` | Requirements, architecture, design, interfaces, test specifications, and product documentation. |
| `04-control/` | Registers, matrices, requests, decisions, and other control records. |
| `05-evidence/` | Reviews, execution records, assessment evidence, reports, releases, and handoffs. |
| `authoring/` | Family registry, structured request template, and specification template for maintaining the collection. |

The [document catalog](INDEX.csv) lists every specification's family, type identifier, human title, relative path, and concise summary (`family,type,title,path,summary`). The numbered directories contain authoring specifications rather than completed documents. The table above describes current contents; [authoring/families.json](authoring/families.json) alone defines family responsibilities, boundaries, and order for classification, request validation, placement, and counting. The six existing families remain defaults; extension requires a sourced mission and the controlled procedure in [CONTRIBUTING.md](CONTRIBUTING.md).

[llms.txt](llms.txt) provides an entrypoint for automated readers. [CHANGELOG.md](CHANGELOG.md) records releases and pending changes. The collection is distributed under the [MIT License](LICENSE).

## Adding document specifications

[CONTRIBUTING.md](CONTRIBUTING.md), released version `3.0.0`, requires mission and source discovery before classification, task-to-content-to-case coverage, standardized 5-key Semantic-Discovery YAML frontmatter on both specifications and standalone finished documents, explicit Rule 13 semantic purity, projection rules, representative finished-instance evaluation, and deterministic composition. Use its [structured request template](authoring/request.template.json) and [specification template](authoring/specification.template.md) after reading the method. Required information may share proportionate paragraphs, lists, or sections.

The `authoring/` directory contains those templates and the family registry, outside the catalog count. No installed renderer or validator is supplied. Version `3.0.0` is a breaking major update over `2.1.0` that introduces mandatory 5-key Semantic-Discovery YAML frontmatter across all 144 specifications and finished-document contracts and migrates catalog discovery to [INDEX.csv](INDEX.csv). Historical `1.0.0` and `2.x` requests remain preserved at their recorded Git revisions; do not recompose historical evidence with current rules.

## Using the collection

1. Scan [INDEX.csv](INDEX.csv) (`family,type,title,path,summary`) to shortlist candidate document types matching the purpose and scope of your work.
1. Inspect the leading YAML frontmatter (`title`, `description`, `topics`, `use_when`, `not_for`) of shortlisted specifications to verify applicability and check explicit exclusions before loading full specification bodies.
1. Read the confirmed specification in full to apply its required inputs, finished-document frontmatter contract, structural obligations, projection rules, and quality criteria using established project facts and actual evidence. Missing information remains visible according to that specification. Do not infer mission fitness, execution, or human usability from a structural check.

For example, [software requirements](03-specifications/software-requirements--core.spec.md) describe obligations allocated to a software item, while [software design](03-specifications/software-design-description--software.spec.md) describes its realization. Selection depends on the document's purpose and use boundary, rather than its filename alone.

Finished documents belong with their owning project or in its authorized documentation location. This repository provides the specifications used to author them.

## Reading a specification

Read `Specification edition` in the identity block; the current edition is `1.0` for every specification. When a project binds specification provenance externally in build or layout metadata, finished operational bodies need not repeat inline provenance lines.

- **Required** content appears in every document of that type.
- **Conditional** content applies when the stated condition is met.
- **Optional** content can help explain the subject without obscuring required content.
- **MUST** and **MUST NOT** express requirements and prohibitions; **SHOULD** expresses the normal choice with justified departures; **MAY** expresses an option.

Every specification and every standalone Markdown finished document begins with a YAML 1.2 Semantic-Discovery frontmatter block (`title`, `description` in 60 to 140 neutral words, `topics` 3 to 12, `use_when` 2 to 6, and conditional `not_for` 1 to 5 omitted when empty) free of internal IDs, version strings, hashes, paths, build metadata, and unresolved template delimiters (Rule 13), followed by the GFM H1 heading and body. A format, such as a table or diagram, does not itself determine a document's purpose or content obligations.

## Documentation scope

This repository maintains reusable document specifications, their CSV catalog, and the authoring resources listed above. It can be read directly from a checkout; it supplies no installation scripts, renderer, or automated validator.

Finished project, host, and service documentation belongs in the owning project's or environment's authorized documentation location. Use that owner's established review and publication workflow for changes. The collection prescribes neither fixed paths under a home directory nor a separate directory for proposed documentation.

The owning environment supplies operational agent instructions and determines how its harness loads them. [CONTRIBUTING.md](CONTRIBUTING.md) governs maintenance of this specification library; operational authorization comes from the responsible project or environment.
