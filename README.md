# SYSETUP document specifications

```console
   ____             __
  / __/_ _____ ___ / /___ _____ _/|
 _\ \/ // (_-</ -_) __/ // / _ > _<
/___/\_, /___/\__/\__/\_,_/ .__//
    /___/                /_/
> Systems development company.
```

[sysetup.com](https://sysetup.com/) · [CSV catalog](INDEX.csv) · [JSON catalog](CATALOG.json)

## Overview

This collection (version [3.3.0](CHANGELOG.md#330)) provides **153 Markdown document specifications** across governance, processes, plans, specifications, control records, and evidence. Every specification carries standardized 5-key Semantic-Discovery YAML frontmatter and defines a document's purpose, scope boundaries, authoring inputs, finished-document contract, supported projections, content definitions, and quality criteria.

The collection helps engineers, project owners, operators, reviewers, and automated agents develop documentation grounded in their project's facts and evidence. It supports both manual authoring and automated compilation workflows.

A specification describes what a document needs to accomplish and contain. The finished document is the project-specific result of applying that specification. The collection does not supply project facts, completed records, or operational authorization.

## Repository organization

| Directory or file | Contents |
| --- | --- |
| `00-governance/` | Policies, an internal standard, and an engineering guide. |
| `01-processes/` | Lifecycle processes, runbooks, playbooks, procedures, and work instructions. |
| `02-plans/` | Engineering, operations, assurance, continuity, and maintenance plans. |
| `03-specifications/` | Requirements, architecture, design, interfaces, test specifications, and product documentation. |
| `04-control/` | Registers, matrices, requests, decisions, and other control records. |
| `05-evidence/` | Reviews, execution records, assessment evidence, reports, releases, and handoffs. |
| `authoring/` | Family registry, structured request template, and specification template for maintaining the collection. |
| `INDEX.csv` | Compact RFC 4180 Tier-1 discovery catalog (`family,type,title,path,summary`). |
| `CATALOG.json` | Derived Tier-2 discovery catalog combining family metadata, catalog summaries, faceted `topics`, `use_when`, `not_for`, and projection kinds. |

The numbered directories contain authoring specifications rather than completed documents. [authoring/families.json](authoring/families.json) defines family responsibilities, boundaries, and order for classification, placement, and counting.

[llms.txt](llms.txt) provides an entrypoint for automated readers. [CHANGELOG.md](CHANGELOG.md) records collection versions and changes. The collection is distributed under the [MIT License](LICENSE).

## Using the collection

1. Scan [INDEX.csv](INDEX.csv) (`family,type,title,path,summary`) to shortlist candidate document types matching the purpose and scope of your work.
1. Inspect Tier-2 metadata (`topics`, `use_when`, `not_for`, `projections`) in [CATALOG.json](CATALOG.json) or inspect the full 5-key leading YAML frontmatter (including `description`) of shortlisted specifications to verify applicability and exclusions before loading full specification bodies.
1. Read the confirmed specification in full to apply its required inputs, finished-document frontmatter contract, projection rules, structural obligations, and quality criteria using established project facts and actual evidence. Missing information remains visible according to that specification.

For example, [software requirements](03-specifications/software-requirements--core.spec.md) describe obligations allocated to a software item, while [software design](03-specifications/software-design-description--software.spec.md) describes its realization. Selection depends on the document's purpose and scope boundary rather than its filename alone.

Finished documents belong with their owning project or in its authorized documentation location. This repository provides the specifications used to author them.

## Reading a specification

Every specification follows one uniform structure governed by the single collection version `3.3.0`:

- **Required** content appears in every document of that type.
- **Conditional** content applies when the stated predicate is met.
- **Optional** content helps explain the subject without obscuring required content.
- **MUST** and **MUST NOT** express requirements and prohibitions; **SHOULD** expresses the normal choice with justified departures; **MAY** expresses an option.

Every specification and every standalone Markdown finished document begins with a YAML 1.2 Semantic-Discovery frontmatter block (`title`, `description` in 60 to 140 neutral words, `topics` 3 to 12 lowercase `kebab-case` terms, `use_when` 2 to 6 neutral task conditions, and conditional `not_for` 1 to 5 grounded exclusions omitted when empty) free of internal IDs, version strings, hashes, paths, build metadata, and unresolved template delimiters, followed by the GFM H1 heading and body.

When a finished document belongs to a unified operational corpus governed by one root catalog and centralized changelog, corpus-level versioning (`CHANGELOG.md` plus VCS revision), a declared corpus/catalog default maintainer, and external specification provenance in build or layout metadata satisfy those respective metadata obligations without repeating identical headers in every file.

## Adding and maintaining specifications

[CONTRIBUTING.md](CONTRIBUTING.md) (`3.3.0`) defines mission and source discovery, task-to-content-to-case coverage, standardized 5-key Semantic-Discovery YAML frontmatter and semantic purity, projection and presentation rules, representative finished-instance evaluation, deterministic composition, and catalog integration. Use [authoring/request.template.json](authoring/request.template.json), [authoring/specification.template.md](authoring/specification.template.md), and [authoring/families.json](authoring/families.json) when adding or revising specifications, and review overlapping sibling specifications for any needed refactoring.

## Documentation scope

This repository maintains reusable document specifications, their discovery catalogs, and the authoring resources listed above. Finished project, host, and service documentation belongs in the owning project's or environment's authorized documentation location and follows that owner's review and publication workflow.
