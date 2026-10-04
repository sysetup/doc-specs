# Document authoring and management instructions

## Common authoring conventions

- **Specification:** Instructions for authoring one document type, including its use boundary, content obligations, and quality criteria. Apply them to established project facts and evidence.
- **Format:** The representation of content, such as Markdown prose, a table, a diagram, or YAML frontmatter. A format alone does not define a document's purpose or required content.
- **Finished document:** A specific authored record that applies a specification to established project facts and evidence.
- **Required:** Include the stated content in every finished document of that type.
- **Conditional:** Include the stated content when the specification's explicit condition applies. If applicability cannot be established, resolve it or follow the specification's direction for that uncertainty.
- **Optional:** Include the content when it helps the document's purpose without obscuring required content.
- **Client or receiving party:** A conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; state its established name and relationship. When no external party exists, state that the document has no external client. Do not invent a party or put it in the specification ID, filename, or type name.

In specifications, **MUST** and **MUST NOT** state requirements or prohibitions. **SHOULD** states the normal choice; a justified case may depart from it. **MAY** grants an option. Preserve these distinctions when authoring the finished document.

The finished document's body uses GitHub Flavored Markdown (GFM). Its specification determines the title, section roles and order, and suitable forms for content. Verify both structure and support for project claims in supplied facts and actual evidence.

YAML frontmatter is a separate convention, not part of GFM. Each type specification states whether its finished document has frontmatter. When required, place a YAML 1.2-compatible mapping before the body, between opening and closing `---` lines, using only fields defined by that specification under their stated conditions. Fields describe the finished document itself; subject-matter content belongs in the body. Quote strings when an unquoted value could be parsed as another type. When no frontmatter is required, begin with the Markdown body. Include metadata fields, document-control sections, and the client or receiving-party element only as defined by the applicable contract and conventions.

## Document authoring specifications

### Applicability and selection

Consult the selected specifications library before creating a document or substantively updating one. A routine conversational answer is not a document deliverable; a purely mechanical correction does not require reclassification.

1. Resolve the specifications root according to Documentation authority and access below. Do not derive it from the current working directory, search unrelated locations, or silently substitute another library.
2. Read the specifications root's `README.md` for context and terminology and its `INDEX.md` for the current catalog. Apply the Common authoring conventions above. Reuse contents already read only while they remain current.
3. Establish the document's purpose, intended readers, supported decision or action, subject, and use boundary from the authorized request and available facts. Select by purpose and use boundary, not solely by title, filename, acronym, or directory.
4. Prefer a matching specialized variant when its stated conditions apply. Do not use a generic variant that excludes the subject; resolve facts that determine classification instead of guessing.
5. Resolve the selected catalog link against the library root and confirm the actual resolved path, including any symlink target, stays within that authorized tree. Read the linked `*.spec.md` in full before drafting; confirm its Specification ID, identity, selection rules, and boundaries.
6. Select independently for each document in an authorized package and revisit selection when purpose or scope changes. Read additional specifications only for authorized deliverables; do not merge incompatible contracts or create companion documents merely because a specification references them.
7. If the required library, README, catalog, or selected specification is missing, empty, inaccessible, or inconsistent, identify the affected path and stop only dependent authoring. Do not invent a specification or silently fall back to another library.
8. If no catalog entry applies, identify the type as outside library coverage and follow the document's explicit requirements and applicable project conventions. Do not force an unrelated specification or claim conformance. Resolve facts that materially affect classification before selecting a type.

### Authoring and verification

- Obtain the selected specification's authoring inputs from the relevant project sources and evidence. Handle unknown, conditional, and inapplicable document content as that specification directs.
- Apply the common conventions above and the selected specification's Finished-document contract, Content definitions and forms, and Quality criteria. Preserve required, conditional, optional, and normative distinctions; do not add metadata or document-control sections outside that contract.
- Write the finished document for its actual subject. Do not reproduce specification instructions as document content or retain unfilled template scaffolding. Preserve compatible project wording without losing required content.
- Distinguish planned activities, observations, recommendations, decisions, verification, validation, approval, acceptance, and release. Bind claims and references to actual sources and relevant revisions; authorship or a passing check does not establish approval or compliance certification.
- Before completion, check applicable content obligations, unresolved facts, structure, metadata, references, and factual support. For authorized packages, also check consistency and traceability across documents.
- Verify document placement and affected indexes and links using the owning project's conventions or Host documentation change preparation below, as applicable.
- Determine available document checks from the actual authoring environment. Do not assume the specifications library supplies generators, schemas, validators, or packaging tools.

## Documentation authority and access

- Resolve the documentation roots from the adopting environment's configuration. When no alternate roots are specified, use the defaults below. Resolve `$HOME` from the active user environment; require unambiguous absolute roots and keep the three documentation trees distinct and non-overlapping. Do not derive their locations from the current working directory.

| Root role | Responsibility | Default root |
|---|---|---|
| Specifications root | Canonical document authoring contracts, read-only for the authoring consumer. | `$HOME/.agents/doc-specs/` |
| Operations root | Canonical source of current host operations documentation, read-only for the authoring agent. | `$HOME/.agents/doc-operations/` |
| Proposal root | Proposed host documentation changes awaiting publication by the designated responsible entity. | `$HOME/.agents/doc-operations-update/` |

- Keep the specifications, operations, and proposal roles separate. The specifications tree supplies document contracts, not project facts or a destination for finished documents. The proposal tree is not a second source of current operational guidance.
- Classify documentation by the system it describes: host-wide configuration, shared services, runtimes, credentials infrastructure, agent integrations, and maintenance belong to host operations; project-specific documentation belongs with its owning project.
- Consult relevant guidance and proposals through their actual index entries. Confirm resolved document paths, including symlink targets, stay within their declared documentation roots. Use those roots within the access provided by the adopting environment.
- Prepare requested host documentation changes and their affected index entries and references in the proposal root.
- Keep project documentation in its authorized project location. Apply the same authoring specifications there without transferring it to the host proposal tree.
- Treat missing, empty, inaccessible, inconsistent, or incomplete required trees, indexes, and documents as unavailable. An empty directory or placeholder file is not guidance or evidence that no proposals are pending. Missing operational guidance does not block independent authoring whose required sources are available.

## Current guidance and pending proposals

1. Before consulting current operations documentation, check the proposal root's `INDEX.md` and relevant proposal paths for pending changes. Read only documents relevant to the subject being documented.
2. Read the operations root's `INDEX.md` and select the canonical documents applicable to that subject. Revisit the index when the documentation scope changes.
3. Keep pending proposals distinct from current canonical guidance. Resolve conflicting revisions before preparing an update; use a proposal as pending input rather than representing it as published guidance.
4. Before maintaining operations documentation, read its indexed configuration-management policy and apply the document-control requirements relevant to the change. Preserve source document paths, versions, constraints, and procedures outside the requested change.
5. When a required index, source document, or revision is unavailable, identify the affected documentation dependency and stop only the dependent authoring or update. Do not silently substitute another source.

## Host documentation change preparation

- Read applicable canonical documents and existing proposals before editing. Revise the document that already covers the subject instead of creating a duplicate; preserve unrelated pending work and resolve conflicting edits before replacing a proposal.
- Create or modify proposed host documents only in the configured proposal root, using intended canonical relative paths and established directory conventions. Include only new or changed documents and the proposal index; do not copy unchanged documents or recreate the full canonical tree.
- Maintain the proposal root's `INDEX.md` as the index of pending proposals. For each change, identify its action (`add`, `update`, `move`, or `delete`), canonical path, proposal path when applicable, and published revision used as its basis when established. Identify an unknown basis explicitly; resolve it before publication.
- Represent a rename as a move with source and destination paths. Place the proposed document at the destination relative path. Represent a deletion as an index entry identifying the canonical document; do not delete the canonical file or create a replacement document for that entry.
- Prepare affected index entries and references in the same change. Record required changes to the canonical root index in the proposal index; the proposal index is not a replacement for the operations root's `INDEX.md`. Write references for their intended published locations; check them against the proposed final tree, including unchanged canonical documents, proposed moves, and deletions. Confirm resolved source and destination paths stay within their authorized trees.
- Leave publication of proposed documents, including canonical replacement or removal, to the designated responsible entity. Preparing documentation does not authorize or perform publication.
- Keep temporary document replacement files beside their proposal destination and remove them after success or failure. Keep the proposal tree limited to changed documents and its pending-proposal index; do not add staging trees, mirrors, or backup copies.
- Outside the canonical and proposal trees, reference host operations documents by their canonical locations instead of reproducing current host configuration or procedures. Generic software documentation may remain with its software without becoming another source of host operations documentation.
- Before completion, verify proposed placement, index coverage, affected references, preservation of unrelated proposals, and absence of duplicates or temporary artifacts created by the work.
- Keep proposed host documentation changes identified as pending until publication by the designated responsible entity.
- Resolve competing documentation destinations before preparing an update; do not create another copy of current guidance.
