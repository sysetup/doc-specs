---
title: "Data contract specification"
description: >-
  Defines the authoring contract for data contracts governing producer-to-consumer expectations for a bounded dataset, data product, event stream, table, or analytical exchange. Covers contract identity, parties, and agreement state, structural schemas and field-level business semantics, assessable data-quality and freshness or delivery expectations, data sensitivity classifications, privacy and permitted-use rules, schema-evolution compatibility modes, deprecation and breaking-change governance, and conditional bindings to checked machine-readable schema or contract artifacts while keeping proposed targets distinct from bilaterally agreed commitments.
topics:
  - "specifications"
  - "data-engineering"
  - "architecture-and-design"
  - "data-contract"
  - "schema-evolution"
  - "data-quality"
  - "data-governance"
  - "producer-consumer-agreement"
use_when:
  - "A data producer and downstream analytical, operational, or AI consumers need an explicit contract for schemas, semantics, data quality, and evolution rules."
  - "A data engineer or steward is defining freshness, completeness, PII classification, compatibility modes, and breaking-change deprecation policies for a data product."
  - "A reviewer is verifying that human data-contract terms align with controlling machine-readable schema artifacts and distinguish proposed rules from agreed guarantees."
not_for:
  - "Controlling physical, electrical, or transport-level protocol parameters across hardware or software boundaries, which belongs in an interface control document."
  - "Documenting a curated static dataset asset's collection methodology, labeling protocol, and bias profile, which belongs in a dataset specification."
  - "Specifying reproducible test-only input fixtures and generators for a bounded test campaign, which belongs in a test data specification."
  - "Providing read-only consumer syntax lookup for APIs, CLIs, or settings without cross-party quality commitments, which belongs in a technical lookup reference."
---

# Data contract specification

## Identity and selection

- **Specification ID:** `DATA-CONTRACT@core`.
- **Purpose:** Define and govern the structural schema, business semantics, data-quality and delivery expectations, privacy and usage boundaries, and schema-evolution rules agreed between a data producer and its consumers for one bounded data product or exchange.
- **Intended readers:** Data producers, downstream data, analytics, application, and AI consumers, data platform and schema-registry stewards, and privacy or security reviewers.
- **Decision or action supported:** Produce, validate, and consume a data product safely, enforce automated schema and quality checks, plan compatible schema changes or breaking migrations, and determine whether commitments are proposed or actually agreed.
- **Use when:** An operational or analytical dataset, table, topic, event stream, file feed, or data product crosses team, service, or organizational boundaries and requires enforceable schema, semantic, quality, privacy, and change commitments.
- **Scope boundaries:** Govern one bounded data product or tightly coupled entity set sharing one producer, lifecycle, and change authority; exclude physical or transport-layer hardware interfaces, one-off test fixtures, static research-dataset provenance narratives, and automatic legal or compliance certification.

## Authoring inputs and unresolved facts

Obtain the data product or exchange identity, version or edition, delivery channel or storage boundary, accountable producer owner, known consumer roles or consumer-registration scope, and actual agreement state with deciding authorities; structural schema definitions (entities, fields, types, nullability, keys, partitioning, ordering, encoding, and serialization format) and exact business meanings, units, timezones, and sentinel conventions; data-quality rules (completeness, uniqueness, validity, referential integrity, statistical or volume bounds) and delivery or freshness expectations (latency, cadence, backfill, and historical retention) with exact measurement methods and failure-handling actions; data sensitivity and personal-data classifications per field or entity, masking or encryption rules, access prerequisites, permitted and prohibited downstream uses, and deletion or erasure propagation rules; schema-evolution compatibility mode, breaking-change criteria, notice periods, coexistence and migration obligations, and retirement policy; and for any selected machine-readable schema or contract artifact (such as JSON Schema, Avro, Protobuf, SQL DDL, or Open Data Contract Standard YAML), its format, version, locator, revision, precedence rule, validator, and check status.

If a producer owner, consumer agreement, field semantic, unit, quality threshold, privacy classification, erasure propagation rule, compatibility mode, or native validator check is unknown or undecided, record the gap explicitly with its downstream integration consequence, resolving action, and assigned owner only when known. Keep unagreed quality targets, unconfirmed retention windows, or draft schemas visibly marked as `proposed`; do not claim bilateral agreement or active automated enforcement without actual decision and enforcement evidence. Missing privacy classifications or unresolved permitted-use boundaries block claiming clearance for sensitive-data production exchange.

## Finished-document contract

- **Title:** Name the data product, stream, table, or exchange and its covered contract version and identify the document as its data contract.
- **Frontmatter:** Required on standalone GFM documents; omitted on selected machine-readable native schema or data-contract artifacts whose formats manage metadata natively. Begin standalone GFM documents with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), excluding internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values, followed by the H1 title. Contract version, parties, agreement state, compatibility policy, and native check status belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract and this type's projection policy.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish contract identity, parties, and agreement state before schema and semantic definitions; place data-quality expectations and privacy governance before evolution rules and any native schema binding. Heading wording may vary.
- **Presentation:** Scale field tables, quality-rule matrices, and lifecycle notes to the data product's complexity without duplicating raw machine-readable schemas wholesale when a controlled native artifact holds exact serialization syntax. Required roles may share sections while keeping field semantics, quality thresholds, sensitivity tags, agreement states, and native precedence directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Data contract document (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one data-product-specific H1. Contract edition, ownership, agreement state, semantic rules, quality guarantees, privacy terms, and corpus-level governance inheritance where applicable remain body content. | Use GFM prose and structured tables for business semantics, ownership, quality expectations, privacy rules, and change governance. Bind every referenced native schema or contract file by exact version, locator, and digest or revision; changes to either surface require reconciliation before retaining current validity. |
| Machine-readable schema or contract artifact (native) | A native schema or contract file (such as JSON Schema, Avro, Protobuf, SQL DDL, or ODCS YAML) omits Semantic-Discovery YAML frontmatter and retains its format-native identifiers and metadata fields without injected Markdown headings. | The declared schema format and version govern machine-readable syntax, serialization types, and automated compatibility checking. State explicitly which surface controls on conflict; validator status covers only the checked artifact, format version, and mapping, and GFM prose never establishes native schema conformance. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Contract identity, parties, and agreement state | Required | Identify the data product, table, topic, or exchange, contract edition, transport or storage boundary, accountable producer owner, registered or intended consumer roles, exclusions, client or receiving-party element when applicable, and truthful contract state (`proposed`, `agreed`, `deprecated`, `superseded`, or `retired`) with actual decision basis. |
| Schema and semantic definitions | Required | Define included entities, fields or columns, logical and physical types, requiredness and nullability, primary, unique, or foreign keys, partitioning or event-time ordering semantics, exact business meanings, allowed value domains or enumerations, units, timezone and character-encoding rules, and handling of missing, default, or sentinel values. |
| Data quality and service-level expectations | Required | Define assessable data-quality rules (completeness, uniqueness, validity, referential integrity, volume or distribution bounds) and operational delivery rules (freshness, latency, update cadence, backfill behavior, historical availability). For each rule, specify exact measurement method, evaluation window, enforcement point, breach response or quarantine handling, and whether it is `proposed` or `agreed`. |
| Privacy, security, and access governance | Required | Classify entity and field sensitivity (such as personal data, special-category data, confidential, or public), state masking, tokenization, or encryption rules, access-control prerequisites, permitted and prohibited downstream uses (including analytics or AI training boundaries where applicable), retention and deletion or erasure propagation obligations, and citations to controlling privacy assessments or policies when they exist. |
| Evolution, compatibility, and deprecation lifecycle | Required | Declare the schema-evolution compatibility policy (such as backward, forward, full, or breaking-versioned), exact rules separating non-breaking from breaking changes, versioning and dual-run coexistence rules, minimum deprecation notice windows, migration and backfill responsibilities, change decision authority, and retirement procedures. |
| Native schema and contract binding | Conditional when one or more machine-readable schema or data-contract artifacts are selected | Identify each selected native format and version, controlling artifact locator and revision or digest, field-level precedence on conflict between GFM narrative and native artifact, compatibility or schema validator tool, and actual check status (`pass`, `fail`, `inconclusive`, or `not-run`). Re-check after any schema, mapping, or prose edit. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Contract identity and state | Exactly one bounded data-product identity, contract edition, and current state in Contract identity, parties, and agreement state. | Use `proposed`, `agreed`, `deprecated`, `superseded`, or `retired`. `agreed` requires recorded concurrence from producer and established consumer or governance authority; publication alone does not establish agreement. |
| Producer and consumer party | One accountable producer role plus one or more identified consumer roles (or explicit open-catalog consumer scope) in Contract identity, parties, and agreement state. | Separate operational contact points from change-approval authority; an unassigned owner remains an explicit gap. |
| Schema field and semantic rule | One entry per governed field or entity attribute in Schema and semantic definitions (or explicit pointer to a bound native schema paired with complete semantic, unit, and sentinel rules). | State type, nullability, key role, business meaning, unit or timezone, and domain constraint; a raw column name alone is not a semantic definition. |
| Quality and delivery rule | One or more assessable quality or freshness expectations in Data quality and service-level expectations, or an explicit statement that no automated quality guarantee is established. | State exact metric, threshold, window, measurement source, breach action, and `proposed` versus `agreed` state. Distinguish defined expectations from observed runtime compliance. |
| Data classification and usage rule | One sensitivity and permitted-use account covering the full contract scope plus field-level annotations for sensitive fields in Privacy, security, and access governance. | State classification, protection mechanism, access prerequisite, downstream use restrictions, and erasure propagation; unknown sensitivity blocks claiming production readiness for personal data. |
| Compatibility and change rule | Exactly one compatibility policy and breaking-change lifecycle rule in Evolution, compatibility, and deprecation lifecycle. | Name allowed non-breaking changes, breaking-change triggers, notice period, coexistence duration, and approving authority. Unspecified change types are not implicitly backward compatible. |
| Enforcement and breach response | One operational enforcement account in Data quality and service-level expectations. | State whether validation is enforced at build time, ingestion, schema registry, or monitoring, what happens to invalid records (reject, dead-letter, quarantine, alert), and escalation owner. Label unimplemented checks as planned. |
| Native contract artifact | Zero or more bound machine-readable schema or contract files in Native schema and contract binding. | Bind format, version, locator, revision or digest, conflict precedence, validator, and check outcome per artifact; one artifact's check never validates another format or revision. |

Use structured tables for schema fields (name, type, nullability, sensitivity, business meaning, domain/unit), quality and freshness rules, and native artifact bindings, paired with concise prose for party responsibilities, privacy usage limits, and deprecation workflows. Reference large machine-readable schemas by exact locator and revision rather than duplicating raw schema payloads across prose and code files. Do not insert blank field rows, sample personal records, or unverified enforcement claims.

## Quality criteria

- Contract identity, producer and consumer roles, transport boundary, and truthful agreement state are explicit; proposed guarantees remain distinguishable from agreed commitments.
- Schema fields specify exact types, nullability, keys, business semantics, units, timezones, and missing-value rules sufficient for independent producer and consumer implementation.
- Data-quality and delivery rules state unambiguous measurement definitions, evaluation windows, enforcement status, and breach or quarantine actions without presenting expectations as observed compliance.
- Sensitivity classifications, masking or access prerequisites, downstream use restrictions, and retention or erasure propagation obligations cover the full data scope and expose unresolved privacy gaps.
- Compatibility modes, breaking-change criteria, deprecation notice periods, dual-version coexistence, and change authorities are explicitly defined.
- Any bound native schema or data-contract artifact states its format, version, locator, revision, precedence on conflict, validator, and own actual check status rather than inferring conformance from GFM prose.
