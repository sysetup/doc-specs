---
title: "Elicitation and source record specification"
description: >-
  Defines the authoring contract for elicitation and source records preserving raw statements, behavioral observations, acquired source artifacts, instrument bindings, permission and custody bases, explicit transformations or redactions, and capture gaps from one bounded collection event or source set prior to synthesis or interpretation. Keeps raw factual provenance cleanly separate from downstream analysis, prevents asserting participant consent without evidence, and documents incomplete or failed capture truthfully.
topics:
  - "evidence"
  - "product-and-discovery"
  - "requirements-engineering"
  - "elicitation-record"
  - "raw-evidence"
  - "source-provenance"
  - "custody-and-consent"
  - "capture-gaps"
use_when:
  - "An interview, workshop, survey, observation, or source-acquisition session has started and raw outputs must be preserved before interpretation."
  - "A researcher or analyst is documenting raw statements, applied instruments, permission provenance, redactions, and capture gaps."
  - "A reviewer is tracing synthesized findings or requirements back to unedited raw collection records and custody rules."
not_for:
  - "Designing interview prompts or questionnaires before collection, which belongs in an elicitation instrument specification."
  - "Presenting interpreted themes, patterns, and product implications, which belongs in user and context research findings."
  - "Recording ordinary project coordination meetings, which belongs in an engineering meeting record."
---

# Elicitation and source record specification

## Identity and selection

- **Specification ID:** `ELICITATION-RECORD@core`.
- **Purpose:** Preserve actual elicitation statements, observations, and raw-source provenance before interpretation.
- **Intended readers:** Researchers, requirements analysts, authorized evidence custodians, and reviewers tracing findings to sources.
- **Decision or action supported:** Recover what was actually collected, under which instrument and permissions, and distinguish it from later interpretation.
- **Use when:** An elicitation or source-acquisition activity has started and its actual material or capture failure needs a durable record.
- **Scope boundaries:** Preserve one bounded collection event or coherent acquired source set; exclude instrument design, synthesized findings, requirements endorsement, and an assertion of consent without evidence.

## Authoring inputs and unresolved facts

Inspect the actual event or acquired sources, capture context and timing, participant codes or source identities permitted for the audience, instrument and notice editions when used, actual permission basis, recordings or notes, capture failures, transcription or redaction transformations, custody, access, retention, and correction history.

Expose unknown provenance, time, instrument edition, permission, completeness, or transformation with its effect, resolving action, and assigned owner if known. Missing permission prevents unrestricted use or sharing; a missing recording cannot be recreated as a verbatim transcript. Record failed capture and uncertain passages. Do not invent participation, quotations, consent, observations, or source identifiers.

## Finished-document contract

- **Title:** Identify the elicitation event or source set and name its elicitation and source record.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish the actual event, provenance, and permitted use before acquired items; follow items with transformations, gaps, and custody. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Elicitation and source record (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Event identity, scope, and permitted use | Required | Identify actual collection boundary, context, captured time and precision or gap, performer, instrument edition when used, source or participant-code scheme, permissions, exclusions, and the client or receiving-party element when applicable. Record consent only from actual evidence and its scope. |
| Acquired material | Required | Preserve one entry per actual statement, observation, note segment, or acquired artifact, with source locator and context. Distinguish direct quotation, paraphrase, observed behavior, and annotator comment. If capture failed, identify the actual attempt and missing material instead of inventing entries. |
| Transformations and corrections | Required | Identify transcription, translation, normalization, selection, redaction, and later corrections actually applied, their performer or tool when known, source-to-derived relationships, and uncertain or unreadable segments. Preserve original material under the established access rules. |
| Completeness, custody, and limitations | Required | State acquired and missing scope, interruptions, provenance and clock limits, access restrictions, retention or deletion basis, custodian or assignment gap, and the permitted handoff. Link existing findings or requirements without treating their later interpretation as raw evidence. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Collection event or source set | Exactly one bounded event or coherent source set in Event identity, scope, and permitted use. | Actual collection or acquisition must have started; a scheduled interview alone does not qualify. |
| Source item | Zero or more acquired items in Acquired material. | Zero requires an actual capture-failure or assessed-empty explanation; each item retains a recoverable locator and source context. |
| Statement kind | Exactly one kind per textual item in Acquired material. | Use verbatim, paraphrase, observation, or annotation; uncertain transcription remains marked uncertain and cannot be called verbatim. |
| Transformation | Zero or more actual transformations in Transformations and corrections. | Identify input, output, operation, and change in meaning or disclosure; redacted derivatives do not silently replace originals. |
| Permission and custody basis | Exactly one account for the record in Event identity, scope, and permitted use and Completeness, custody, and limitations. | Describe actual allowed uses, access, storage, and retention; a participant code is not a guarantee of anonymity. |
| Capture gap | Zero or more gaps in Completeness, custody, and limitations. | Name missing scope and effect; no gap implies absent participants or absent feedback unless the observations establish that. |

Use timestamped segments or an item table linked to access-controlled recordings, transcripts, or notes. Keep sensitive raw material outside a broadly shared GFM document; retain permitted excerpts and locators. Raw originals remain the acquisition authority, with derived excerpts and corrections explicitly identified.

## Quality criteria

- The event occurred or acquisition started, and its context, instrument, permission scope, and provenance are recoverable or explicit gaps.
- Every acquired item identifies its source and statement kind; capture failure creates no invented transcript or observation.
- Transformations and corrections retain traceability to originals, including uncertainty and actual redactions.
- Missing coverage, custody, permitted sharing, and retention constrain downstream use; later findings do not rewrite raw sources.
