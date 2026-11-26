# Specification authoring standard

Version: `3.3.0`. Status: active repository standard governing all catalog specifications, discovery catalogs, authoring templates, and the family registry.

This standard governs the creation of new document-type specifications and the revision of existing specifications across the collection. Every specification in the live collection conforms uniformly to this edition.

## Start here

Read [README.md](README.md), [INDEX.csv](INDEX.csv), [CATALOG.json](CATALOG.json), this standard, and close alternatives using progressive disclosure: scan [INDEX.csv](INDEX.csv) to shortlist candidates, inspect Tier-2 metadata in [CATALOG.json](CATALOG.json) or the leading YAML frontmatter of candidate files to confirm applicability and exclusions, and read full specification bodies only for relevant matches. Establish the mission and its sources before selecting a family or settling literal text. Prepare a request from [request.template.json](authoring/request.template.json), evaluate finished instances against the candidate contract, compose using [specification.template.md](authoring/specification.template.md), and complete all acceptance gates.

This standard is the normative source for the method. [families.json](authoring/families.json) is the sole authoritative definition of family responsibilities, boundaries, and order. The templates project these rules. All three maintenance resources under `authoring/` remain outside the catalog count.

## Scope, authority, and interpretation

**GOV-01 — Two authoring levels.** A specification is a reusable contract for a document type. A finished document is an instance grounded in one project's facts. This standard controls specifications. The selected specification controls the finished document. Do not copy project-specific facts, host-specific paths or instructions, completed evidence, or operational authorization into a reusable specification.

**GOV-02 — Permission boundary.** These rules confer no filesystem, network, execution, installation, approval, or publication permission. Apply the active user's authorization and the owning environment's instruction hierarchy.

**GOV-03 — Normative vocabulary.** Uppercase `MUST` and `MUST NOT` identify obligations and prohibitions, `SHOULD` identifies a default requiring a stated reason for departure, and `MAY` identifies an option. A requirement can also be stated as a direct imperative within this standard. Lowercase uses are ordinary prose. The convention follows [RFC 8174](https://www.rfc-editor.org/rfc/rfc8174).

**GOV-04 — No silent exceptions.** A contribution that violates a rule is blocked under this version. Record the rule, conflict, consequence, and needed decision. Revise this standard before introducing an exception. A pending request or absent objection is not an exception.

**GOV-05 — Controlled changes.** One single project version identifies the entire collection (`CONTRIBUTING.md`, `authoring/families.json`, `authoring/request.template.json`, `authoring/specification.template.md`, `INDEX.csv`, `CATALOG.json`, `README.md`, `llms.txt`, `CHANGELOG.md`, and all `*.spec.md` files). Any specification addition, specification revision, or method update increments the single project version and records the change in [CHANGELOG.md](CHANGELOG.md). Keep this standard, templates, catalogs, and affected specifications synchronized in the same change.

**GOV-06 — Single-version alignment.** All live specifications share the active project version and conform uniformly to its structure without legacy format exemptions. A major increment changes a required interface or obligation, a minor increment adds specifications or compatible capabilities, and a patch corrects defects without breaking contracts. Bind the family registry by version and digest; a registry change requires coordinated review across this standard, templates, catalogs, placement, and counts.

## Standardized Semantic-Discovery YAML frontmatter contract

**FM-01 — Mandatory 5-key schema.** Every `.spec.md` file in this collection and every standalone Markdown finished document governed by a specification MUST begin on line 1 with a YAML 1.2-compatible mapping delimited by `---` lines containing ONLY these five closed keys in this exact order (no extra or undeclared keys):

| Key | Requirement | Type and bounds | Purpose |
| --- | --- | --- | --- |
| `title` | Required | String, 3–160 characters | Source-grounded specification or document title used for identity and first-pass semantic matching. |
| `description` | Required | String, 60–140 words | Compact, information-dense, neutral semantic retrieval summary covering purpose, subjects, reader decisions, and boundaries. |
| `topics` | Required | Array of 3–12 unique lowercase `kebab-case` strings (2–80 characters each, matching `^[a-z0-9]+(?:-[a-z0-9]+)*$`) | Faceted subjects combining 2–3 shared controlled domain tags with concrete spec-specific subjects, methods, or artifacts. |
| `use_when` | Required | Array of 2–6 unique strings (at least 10 characters each) | Natural-language neutral task or intent conditions where consulting the document is relevant; never imperative commands. |
| `not_for` | Conditional | Array of 1–5 unique strings (at least 10 characters each) | High-value exclusions identifying neighboring intents or document types for which the document is unsuitable; omit the key entirely when no grounded exclusion exists. |

Word counts for `description` (and for `INDEX.csv` `summary`) are measured by splitting the trimmed scalar string on runs of ASCII whitespace (`\s+`). Avoid relying on exact boundary counts (60 or 140) where punctuation or edits could push a summary out of range.

For specifications in this collection, `topics` MUST include 2–3 shared controlled domain tags selected from the vocabulary below, followed by 3–5 concrete specification-specific lowercase `kebab-case` tags:

| Controlled topic | Scope |
| --- | --- |
| `governance` | Organizational policies, internal standards, and nonbinding engineering guides. |
| `processes` | Reusable lifecycle processes, SOPs, runbooks, playbooks, and work instructions. |
| `planning` | Forward-looking engineering, operations, continuity, quality, and research plans. |
| `specifications` | Technical definitions, requirements, architecture, design, interfaces, test definitions, and product docs. |
| `control-records` | Living registers, matrices, requests, decisions, backlogs, proposals, and status reports. |
| `evidence` | Performed reviews, execution logs, audits, assessments, baselines, handoffs, and releases. |
| `systems-engineering` | Cross-discipline system lifecycle, CONOPS, SEMP, integration, transition, and retirement. |
| `software-engineering` | Software development, design, maintenance, composition, code review, and PR workflows. |
| `requirements-engineering` | Business needs, stakeholder/system/software/interface requirements, and traceability. |
| `architecture-and-design` | Architecture descriptions, ADRs, trade studies, system/software/network design, and interfaces. |
| `verification-and-validation` | V&V processes, plans, procedures, matrices, and verification/validation evidence. |
| `testing` | Test planning, design, cases, data, environments, procedures, execution, anomalies, and completion. |
| `security` | Cybersecurity policy, security engineering, incidents, advisories, vulnerabilities, access, and certificates. |
| `operations` | Service operations, runbooks, availability, maintenance, observability, and operational execution. |
| `incident-and-continuity` | Incident response, contingency planning, business continuity, and post-incident reviews. |
| `configuration-management` | Configuration items, baselines, change requests, deviations/waivers, and composition tracking. |
| `quality-assurance` | Quality policy/planning, audits, defect tracking, reviews, and acceptance records. |
| `risk-and-safety` | Risk management, FMEA, hazard logs, safety assurance, and assumptions/dependencies. |
| `product-and-discovery` | Roadmaps, backlogs, feedback, user research, elicitation, tutorials, and support guides. |
| `change-and-release` | Changelogs, release notes, release records, transition, and third-party distribution notices. |
| `networking-and-infrastructure` | Network design, allocations, access rules, cabling, IT assets/inventory, and runtime environments. |
| `commercial-and-supplier` | Technical-commercial proposals, contracted agreements, supplier assurance, and effort records. |
| `ai-and-ml` | AI model and system cards, empirical AI evaluations, benchmark suites, and AI datasets. |
| `data-engineering` | Data contracts, schema evolution, data quality rules, curated datasets, and data lineage. |
| `privacy-and-compliance` | Privacy impact assessments, personal-data safeguards, data-subject rights, and compliance records. |

**FM-02 — Frontmatter semantic purity and template hygiene.** Frontmatter values MUST carry pure semantic retrieval signal only. Every value across `title`, `description`, `topics`, `use_when`, and `not_for` MUST NOT contain:

- Internal specification or document identifiers (such as `TYPE@variant` IDs, requirement codes, or rule codes).
- Version strings, release editions, or build numbers.
- Commit hashes, cryptographic digests, or pipeline metadata.
- Filesystem paths, numbered directory prefixes, repository filenames, or home-directory tokens.
- Unresolved template delimiters (`{{`, `}}`, `{%`, `%}`).

The leading YAML frontmatter block precedes the mandatory GFM H1 heading and does not replace it. Substantive domain authority, scope, state, and obligations remain in the Markdown body.

## Mission design and finished-instance evaluation

**DES-01 — Independent mission inventory.** Before classification, record the supported decision, actual reader roles and retrieval, decision, or action tasks, subject boundaries, expected lifetime, and consequences of missing information. Obtain authoritative sources with exact editions and locators; distinguish supplied, derived, and synthetic information. For each task, enumerate necessary information independently of existing section names. Inspect applicable source obligations, conditions, multiplicity, states, prerequisites, and stopping rules. A section-to-criterion checklist cannot detect information omitted from the design. An unavailable source that could change the mission blocks the dependent design; do not invent a rule from its title.

**DES-02 — Coverage and exclusions.** Give tasks, obligations, sources, exclusions, and acceptance cases stable local IDs. Trace every task and source obligation to content references and observable cases, or to a justified exclusion with its boundary and source basis. Required task information MUST NOT be excluded. Conditional obligations retain their predicates; undecidable applicability needs an explicit gap and blocks the affected favorable decision. The gap rule identifies missing information, consequence, resolving action, and an actual owner only when assigned. Inspect source-to-inventory coverage as well as inventory-to-content coverage; a structurally valid trace is not semantic sufficiency. References to existing sections and definitions remain necessary, but never replace this independent inventory.

**DES-03 — Representation design.** Set semantic dependencies, repeatable entities, native states, applicable frontmatter, and supported projections from the mission. Preserve native authority and distinguish a view from its controlling source. Required semantic roles MAY share paragraphs, lists, or sections when every obligation remains retrievable and applicable conditions remain explicit. Do not require a heading per role, universal body word counts, or unrelated administrative chapters. A selected variant remains complete and standalone; supporting resources MUST NOT become overrides needed to assemble its obligations.

**EVAL-01 — Representative instances.** Evaluate at least one ordinary finished instance, one incomplete-input instance, and one relevant boundary instance for each new or revised type before declaring the design ready. Bind fixtures and actual evaluation records to the inspected contract and source bytes. Synthetic inputs MUST be labeled. Cases state the reader task, input or trigger, expected retrieval or action, stopping condition, method, and actual outcome. Verify that standalone Markdown finished instances carry valid 5-key Semantic-Discovery YAML frontmatter complying with FM-01 and FM-02. Correctly exposing an unknown or stopping unsafe use can pass an incomplete-input case; inventing the missing fact cannot. Add mission-specific execution or native-format checks when the mission claims those capabilities. Do not claim tutorial readiness without a supported safe walkthrough, native conformance without applicable checks, participant comprehension without an actual assessment, or human usability without real human evaluation. Required unresolved checks block readiness; a justified inapplicable check is a recorded disposition, not a pass.

**EVAL-02 — Clarity and efficiency.** Assess stable terminology, explicit verbs, usable headings or locators, visible sources and unknowns, prerequisites before dependent actions, and sufficient context for each task. Inspect whether the reader can retrieve and use the necessary information without avoidable rereading, irrelevant boilerplate, duplicate masters, or forced presentation depth. Record actual observations and limits separately from expected results. Static inspection, descriptive walkthrough, actual agent use, human evaluation, and measurements are distinct methods. Successful self-inspection does not establish independent review, numerical efficiency, acceptance, or universal mission fitness.

## Selection and placement

**SEL-01 — Reuse before addition.** Search [INDEX.csv](INDEX.csv) by family, title, and summary, then inspect candidate metadata in [CATALOG.json](CATALOG.json) or candidate YAML frontmatter before reading close alternatives in full. If an existing specification already serves that purpose and boundary, use it; a new project, customer, language, heading preference, or output format does not establish a new type.

**SEL-02 — Type and variant.** Use a new type when its supported decision or content responsibility is materially different. Use a new variant of an existing type when that responsibility remains the same but applicability changes substantive obligations. Record the difference against each existing variant of that type. A variant is a complete standalone specification: it MUST NOT require a reader to assemble a base specification and an override. Neither a `core` variant nor a generic base file is required for a specialized family.

**SEL-03 — Family decision.** Assign exactly one registered family by the mission's primary responsibility, using [families.json](authoring/families.json). Classification, request validation, placement, and counts MUST read the same registry rather than maintain independent lists. Classify the job, not its title, form, or publication state. If two responsibilities remain plausible, resolve the mission boundary rather than use a directory number as a tie-break.

**SEL-04 — Identity derivation.** A type matches `[A-Z][A-Z0-9]*(?:-[A-Z0-9]+)*` and a variant matches `[a-z][a-z0-9]*(?:-[a-z0-9]+)*`. Each is at most 64 ASCII characters. Derive the ID as `TYPE@variant` and the repository path as `family/lowercase(TYPE)--variant.spec.md`. IDs and paths are unique across the contribution and catalog. Existing variants of a type stay in its established family. A client name, instance ID, revision, or date MUST NOT become part of this type identity.

**SEL-05 — Multiple additions.** Specify each document's decision and content boundary separately. If two proposed files have the same purpose, boundary, and obligations, collapse them into one before composition. If close variants overlap, record an explicit selection rule; an unresolved overlap blocks readiness. In a batch, compose files in ascending ASCII ID order. When adding a new specification, inspect existing siblings and refactor overlapping scope boundaries, `not_for` exclusions, or shared definitions as needed so the catalog stays coherent.

**SEL-06 — Controlled family extension.** When no registered responsibility fits a sourced mission, retain a `draft` request with a `family_extension` proposal. Record the proposed directory, substantive responsibility and boundary, unmet mission, source IDs, analysis against every registered family, migration and consumer impact, and actual decision state. An unrestricted miscellaneous category is prohibited. A proposal alone never enables placement or counting. Before a ready request may use the family, an authorized decision must establish it, [families.json](authoring/families.json) and the project version must update together under GOV-05 and GOV-06, and classification, templates, placement, counts, links, and discovery catalogs must be checked together.

The registry in [families.json](authoring/families.json) is UTF-8 JSON with sorted object keys containing exactly `families` (nonempty ordered array) and `version` (project version string). Each family has exactly `boundary`, `directory`, and `responsibility` (nonempty strings, sorted alphabetically). Directory names are unique and match `[0-9]{2}-[a-z][a-z0-9]*(?:-[a-z0-9]+)*`; their resolved paths stay inside the library. Array order controls placement. Reject duplicate keys and unregistered live specification directories.

## Required request

**REQ-01 — Input states.** The request is UTF-8 JSON, using the shape in [request.template.json](authoring/request.template.json) with object keys ordered alphabetically by Unicode code point at every nesting level. Reject duplicate keys before discarding object-key occurrences; a parser's last-value behavior is insufficient. Reject unknown keys and wrong value types in either state. `draft` permits unresolved design strings and template markers, including a marker standing in for a string enumeration such as family. `version` and `state` themselves are always valid literals. `ready` requires all value rules and means the authoring decisions and literal wording are settled for composition. Do not compose catalog files from `draft`.

**REQ-02 — Exact shape.** Objects have exactly the keys specified below. JSON object-key order has no application meaning, while repository source files sort object keys lexicographically for deterministic diffs; array order has the meaning stated here. Arrays are nonempty unless explicitly allowed to be empty. No value is inferred or silently defaulted.

| Object | Keys and types |
| --- | --- |
| Request | `base_revision`: full library HEAD object ID; `items`: array of item objects; `source_bindings`: array of binding objects; `state`: `draft` or `ready`; `version`: current project version string (`3.3.0`). |
| Binding | `path`: library-relative file path; `sha256`: lowercase 64-hex digest of its inspected working-tree bytes. Paths are unique and resolve, including symlinks, inside the authorized library. |
| Item | `authoring`: authoring object; `comparisons`: array of comparison objects; `contract`: contract object; `definitions`: array of definition objects; `design`: design object; `family`: registered directory; `family_extension`: null or extension object; `forms`: string; `frontmatter`: specification-frontmatter object; `identity`: identity object; `operation`: `add` or `revise`; `previous_sha256`: null for add, inspected prior digest for revise; `quality`: array of criterion objects; `supporting`: array of support objects, possibly empty. |
| Extension | `alternatives`, `boundary`, `directory`, `migration_impact`, `responsibility`, `unmet_mission`: strings; `decision`: null while pending, otherwise the actual decision locator and authority; `source_ids`: array of design-source IDs; `status`: `pending`, `authorized`, or `rejected`. A draft may name an unregistered proposed directory only through this object. |
| SpecFrontmatter | `description`: 60–140 word neutral semantic summary complying with FM-02; `not_for`: optional array of 1–5 grounded exclusions (omit key when empty); `title`: derived specification title matching `catalog_name` plus `" specification"` without duplicating `"specification"` when `catalog_name` already ends with it; `topics`: array of 3–12 unique lowercase `kebab-case` terms (including 2–3 controlled domain tags from FM-01); `use_when`: array of 2–6 unique neutral task conditions. |
| Design | `cases`: array of case objects; `change_basis`, `lifetime_and_risk`, `subject_boundary`, `unknown_facts`: strings; `coverage`: array of trace objects; `exclusions`: array of exclusion objects, possibly empty; `obligations`: array of obligation objects; `sources`: array of source objects; `tasks`: array of task objects. |
| Source | `authority`, `id`, `locator`, `version`: strings. Give exact source and version and inspected local digest where applicable; identify synthetic sources explicitly. An unknown edition remains a limitation and blocks decisions depending on it. |
| Task | `action`, `id`, `reader`: strings; `information`: array of strings enumerating independently identified necessary information. |
| Obligation | `applicability`, `id`, `information`: strings; `source_ids`: array of source IDs. Applicability states an explicit required scope or a decidable condition. |
| Exclusion | `id`, `information`, `reason`: strings; `source_ids`: array of source IDs. Explain the bounded rationale; do not exclude required task information. |
| Trace | `case_ids`, `content`, `exclusion_ids`, `obligation_ids`, `task_ids`: arrays of references, possibly empty individually. Each row names at least one task or obligation and at least one case; it maps to content or a justified exclusion, never both. Tasks map to content. Every task and obligation has a trace; every exclusion is used. |
| Case | `evidence`, `expected`, `fixture`, `id`, `procedure`: strings with actual locations or an explicit not-run gap; `kind`: `ordinary`, `incomplete`, or `boundary`; `result`: `pass`, `fail`, `inconclusive`, or `not-run`. Ready requires checked passing cases of all three kinds, not merely filled fields. |
| Identity | `catalog_name`, `catalog_summary`, `decision`, `purpose`, `readers`, `scope`, `type`, `use_when`, `variant`: strings. Type and variant follow SEL-04. `catalog_name` is the human document-type name without a trailing `"specification"` unless part of the domain title. `catalog_summary` is one concise Tier-1 summary line for `INDEX.csv` (8–18 words, no trailing period). |
| Comparison | `difference`: string explaining the inspected difference in responsibility, applicability, or obligations; `id`: a real existing specification ID, or another proposed ID in this batch. |
| Authoring | `inputs`: complete paragraph of required authoring inputs; `notes`: array of zero or more additional concise paragraphs for subject-exclusion or boundary rules when needed; `unresolved`: complete paragraph defining gap handling and blocking conditions. |
| Contract | `frontmatter`: finished-document frontmatter object; `order`, `presentation`, `title`: strings; `projections`: array of projection objects; `sections`: array of section objects in semantic dependency order. |
| FinishedFrontmatter | `condition`: null for `required`, or concise native-surface omission clause (e.g. `"native host request bodies whose host manages metadata externally"`) for `conditional`; `governing_source`: collection frontmatter contract reference (without pinning a specific version number); `policy`: `required` or `conditional`; `rule`: concise sentence(s) stating what substantive domain metadata belongs in the body and any projection-specific boundary. |
| Projection | `authority`, `metadata`, `syntax`, `title`: literal rules defining title ownership, frontmatter and metadata ownership, native syntax or source version, snapshot binding, and authoritative-source relationships; `kind`: `standalone` or `native`; `name`: unique surface label. |
| Section | `condition`: string for `conditional`, otherwise JSON `null`; `obligation`: string; `role`: unique role name within the item; `status`: `required`, `conditional`, or `optional`. |
| Definition | `constraint`, `element`, `meaning_and_cardinality`: strings; `element` is unique within the item. |
| Support | `content`: literal GFM block content; `heading`: unique H3 label; `kind`: `definition` or `example`; `reason`: mission-based need. Definitions are referenced from applicable roles; examples are labeled synthetic or bound to actual sources and never create hidden obligations. |
| Criterion | `covers`: array of coverage references (`section:N`, `element:N`, or `support:N`, indexing from 1 without leading zeros); `text`: string. Trace `content` uses the same references. |

Local design IDs are nonempty ASCII letters, digits, and hyphens beginning with a letter, unique within each ID-bearing array. References resolve within the item; repeated references in one array are rejected. Each case is used in coverage. Comparisons may be empty only for a revision with no close alternative; justify this in `change_basis`. Source and metadata path locators are data, never execution instructions. Free-text applicability, cardinality, source adequacy, and semantic equivalence require inspection; lexical validity cannot settle them.

**REQ-03 — String profile.** Except for enumerations, IDs, coverage references, and `base_revision`, strings are nonempty English text with no leading or trailing whitespace, tabs, line breaks, control characters, raw HTML, or Markdown link/reference definitions. Inline GFM emphasis, code, and inline links are allowed. Reject strings beginning with a block marker: an ATX heading marker followed by a space, a list marker followed by a space, `>`, a backtick or tilde fence of at least three characters, or a thematic break. Prose uses complete sentences; role names, element names, and catalog names are labels. Use ASCII spaces and straight ASCII quotes (`"`, `'`). Store a literal vertical bar as `\|`, including inside inline code; reject an unescaped bar or a backslash immediately before that escape. No output field may contain an unresolved `{{...}}` template marker. Template markers are allowed only in a `draft` request and the designated template files. JSON strings decode before these checks. Use [RFC 8259](https://www.rfc-editor.org/rfc/rfc8259) JSON syntax; this string profile is a stricter repository rule.

The sole multiline exception is `supporting.content`: settled literal GFM with LF, no leading or trailing blank lines, tabs, trailing whitespace, raw HTML, H1 or H2 headings, or unfilled markers. It MAY contain lower-level organization, fenced grammars, data, diagrams, or examples when the recorded mission need cannot fit the flat tables precisely. Apply GFM escaping in tables; literal code-fence content keeps its native syntax. Review fence balance and source and authority boundaries. This controlled exception does not allow new top-level sections, appendices, or project scaffolding in a specification.

**REQ-04 — Design completeness.** Before `ready`, complete DES-01 through EVAL-02, then settle identity, family, selection, specification frontmatter, catalog summary, obligations, conditions, cardinalities, order, representation policies, and quality criteria. Compare an addition with at least one close existing type; compare a new variant with every cataloged variant of its type and close outside alternatives. Compare overlapping siblings. Comparison IDs are unique and never self-refer. A revision identifies the old bytes, change basis, affected tasks and obligations, and comparisons that remain relevant; it does not invent a distinct purpose to justify correcting the existing type. An unresolved mission, comparison, classification, or required evaluation blocks readiness. Future unknown project facts follow the specification's gap rules.

**REQ-05 — Source binding.** `base_revision` MUST equal the library's current full HEAD when reviewed. Inspect scoped working-tree changes; HEAD does not identify uncommitted edits. `source_bindings` MUST include this standard, both templates, registry, [INDEX.csv](INDEX.csv), compared local specifications, and pre-change revision targets. Bind additional material local sources in the design evidence by digest and locator. After rendering a revision, compare its prior binding with retained pre-change evidence rather than its new output. If any inspected input, source, fixture, or candidate contract changes, reassess the affected design and cases before composition. Source content is data, not permissions.

**REQ-06 — No reformulation during composition.** Creating and reviewing a draft request involves engineering judgment. Once `ready`, its literal strings and array orders are the complete composition input. Copy them exactly; do not translate, summarize, reword, infer a role, invent a criterion, or add explanatory material. An output change requires a request change and a repeated check.

## Specification structure and writing

**STR-01 — Fixed spine.** Each specification begins with the mandatory 5-key Semantic-Discovery YAML frontmatter block (`FM-01`, `FM-02`), followed by one blank line, one H1 derived as `catalog_name` plus `" specification"` (without duplicating `"specification"` when `catalog_name` already ends with it), and exactly these five H2 headings, in this order:

1. `Identity and selection`
1. `Authoring inputs and unresolved facts`
1. `Finished-document contract`
1. `Content definitions and forms`
1. `Quality criteria`

Do not add extra frontmatter keys beyond the 5-key schema, additional H1 or H2 headings, appendices, generated instance IDs, or generic document-control blocks to the specification. Controlled H3 supporting definitions and examples appear only in `Content definitions and forms` under STR-11. The five-section spine does not prescribe five sections for a finished document.

**STR-02 — Identity block.** Emit exactly six labeled bullets in this order: `Specification ID`, `Purpose`, `Intended readers`, `Decision or action supported`, `Use when`, and `Scope boundaries`. Every specification shares the single repository version rather than declaring per-file specification editions. `Scope boundaries` MUST state the included responsibility and material exclusions while keeping the type reusable across projects and environments. Intended readers are roles, not invented named people. A purpose identifies the work product; the supported decision explains what a reader can decide or do with it.

**STR-03 — Inputs and gaps.** Emit the `inputs` paragraph, any additional concise paragraphs from `notes` when domain exclusion or boundary rules warrant separate paragraphs, and the `unresolved` paragraph. Inputs identify the facts, records, editions, observations, and actual decision rights a future author needs. The gap rule states how to expose a missing fact, its consequence, resolving action, and actual owner if assigned. It identifies which unresolved authority, criterion, configuration, or safety condition prevents a favorable state or operational use when relevant. It distinguishes unknown, inapplicable, proposed, and observed facts without inventing owners, dates, evidence, thresholds, or approval.

**STR-04 — Finished-document contract.** Emit exactly five labeled bullets in order: `Title`, `Frontmatter`, `Client or receiving party`, `Order`, and `Presentation`. Title, order, and presentation are literal request values.

Render the `Frontmatter` bullet deterministically from `contract.frontmatter`:

- When `policy` is `required`: emit `"Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by \`---\` lines containing \`title\`, \`description\` (60 to 140 neutral retrieval words), \`topics\` (3 to 12 concrete lowercase kebab-case terms), \`use_when\` (2 to 6 neutral task conditions), and conditional \`not_for\` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. "` + `rule` + `" Governing source: "` + `governing_source`.
- When `policy` is `conditional`: emit `"Required on standalone GFM documents; omitted on "` + `condition` + `". Begin standalone GFM documents with a YAML 1.2 Semantic-Discovery frontmatter block delimited by \`---\` lines containing \`title\`, \`description\` (60 to 140 neutral retrieval words), \`topics\` (3 to 12 concrete lowercase kebab-case terms), \`use_when\` (2 to 6 neutral task conditions), and conditional \`not_for\` (1 to 5 grounded exclusions, omitted when empty), excluding internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values, followed by the H1 title. "` + `rule` + `" Governing source: "` + `governing_source`.

Quote ambiguous YAML scalar strings. Unknown required metadata blocks the affected publication rather than being invented. Omitted, false-condition, and unknown metadata remain distinct.

The `Client or receiving party` bullet is the collection's fixed common rule:

> Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.

The client rule applies independently of role status and projection; integrate it in ordinary identity or scope context when present.

**Uniform corpus-level governance inheritance:** Across all specification families (governance, processes, plans, specifications, control records, and evidence where applicable), when a finished document belongs to a unified operational corpus governed by one root catalog and centralized changelog:

- A corpus-level version tracked in the corpus changelog plus its controlling VCS revision satisfies document edition or version identification without repeating local per-document edition headers.
- An explicit default maintainer declared at the corpus or catalog level satisfies maintenance-responsibility identification without repeating identical default responsibility headers in every file, provided any non-default owner is stated explicitly.
- External build, catalog, or layout metadata satisfies specification provenance without requiring inline provenance lines inside rendered operational document bodies.

Order agrees with semantic dependency order, not a mandatory heading list. `Presentation` explicitly allows proportionate grouping while preserving every required fact.

**STR-05 — Projection rules.** Emit a projection table after the five contract bullets and before the role table: `| Projection | Title and metadata ownership | Syntax and source authority |`, followed by `| --- | --- | --- |`. Every specification MUST declare at least one projection (`standalone`, and `native` wherever an external host, board, form, or machine-readable schema surface applies). The first cell combines `name` and parenthesized `kind`; the second combines `title` and `metadata` separated by one space; the third combines `syntax` and `authority` separated by one space. Every standalone GFM projection carries the mandatory 5-key Semantic-Discovery YAML frontmatter followed by its own H1. A native host surface follows its explicit surface rule without redundant H1s, copied masters, or unsupported YAML injection. Declare the inspected snapshot and what happens when host metadata changes. A native authoritative artifact remains controlling; a GFM view cannot silently change syntax, field meanings, legal text, or source state.

**STR-06 — Role table.** Use exactly the header `| Section role | Status and inclusion condition | Content obligation |`, followed by `| --- | --- | --- |`. Emit one row per section object. Render `required` as `Required`, `optional` as `Optional`, and `conditional` as `"Conditional when "` plus its condition. A conditional condition is a decidable predicate over authoring inputs, without a leading `when` or a terminal period. At least one role is `required`. Each role has substantive content and a unique name. Do not place coverage caveats, cardinality notes, or punctuation extensions in the status column; keep them in `Content obligation`.

**STR-07 — Inclusion semantics.** A required role always appears in the finished document, including an explicit no-items statement when its permitted cardinality is zero. A conditional role appears when its predicate is true and is omitted when false; place a material exclusion reason in the applicable scope role. If the predicate cannot be decided, expose the gap and block readiness of the affected content or decision. An optional role may be omitted, but its constraints apply whenever it is included. A mandatory obligation cannot be hidden in an optional role. An inapplicable concern and a missing fact are distinct.

**STR-08 — Element table.** Use exactly `| Element | Meaning and cardinality | Constraint |`, followed by `| --- | --- | --- |`. Emit one row per definition object. Define each controlled entity, state, relationship, recurring item, evidence or result distinction, or special vocabulary needed to interpret the role obligations. State an explicit cardinality: exactly one, zero or one, one or more, zero or more, one per identified item, or a clearly stated conditional count. Define allowed state values and legal transitions where the type controls states. A definition does not create an obligation by itself; identify the role that requires the element.

**STR-09 — Forms paragraph.** Emit the `forms` paragraph after the element table. Recommend prose, tables, lists, or diagrams based on the subject and decision. Define which content remains authoritative. Do not mandate a format because another type uses it. Do not insert blank record rows, sample project facts, copied executable configuration, or a mandatory unrelated appendix. A command example never establishes authority to run it.

**STR-10 — Quality criteria.** Emit one bullet for each criterion's `text`, preserving order. Criteria name observable completeness, consistency, boundary, source, state, or safety conditions. Every section and definition has at least one coverage reference from a criterion. Every criterion has at least one valid reference. Keep coverage references in the request; do not add them to the specification. A criterion assesses the specified document content; it does not manufacture a test result, product conformity, acceptance, or effectiveness claim.

**STR-11 — Supporting content.** After forms, emit each support's H3 heading and literal content in array order. Its kind and reason remain design evidence. Include support references in quality coverage and mission traces. A normative definition must be invoked by the relevant role; an example cannot conceal a required rule or invent actual project evidence. Use supporting content only when it improves precision beyond the flat definitions, and keep all selected obligations inside the standalone specification.

**TXT-01 — Editorial rules.** Write in English, with direct active verbs and stable domain terminology. Use `Obtain`, `Inspect`, `Identify`, `State`, `Define`, or `Record` when they accurately describe the authoring obligation. Prefer short connected prose for purpose and rationale, tables for repeated structured obligations, and bullets for distinct checks. Keep qualifications with the obligation they limit. Replace vague claims such as "complete," "appropriate," or "secure" with the items, bounds, or decision basis the reader must inspect. Use normative capitals for material obligations or prohibitions, rather than decorating every sentence.

**TXT-02 — Evidence and scope.** Describe planned work in plans, required or intended properties in definitions and designs, current control in registers, and actual observations in evidence records. Domain-specific exceptions follow the selected document's responsibility. A link or digest does not prove approval; a proposed action is not performed work; a planned criterion is not a result. Preserve distinctions among review, approval, execution, verification, validation, acceptance, and publication wherever the type uses them. Reference another actual record when it exists; provide a truthful direct statement or gap when it does not. Do not require a fabricated dependency record to complete a document.

## Deterministic composition

**CMP-01 — Text encoding.** Specification Markdown files use UTF-8 without BOM, LF line endings, no tabs, no trailing whitespace, and one final LF. Headings, bullets, table rows, and ordinary paragraphs occupy one physical line. Supporting content preserves its settled physical lines, including intentional internal blank lines. Join output blocks with one empty line; do not hard-wrap, normalize, or reformulate settled input.

**CMP-02 — Block sequence.** Compose the following blocks in order, joining blocks with two LF characters and ending with one final LF. A YAML frontmatter mapping, bullet group, or table is one block whose lines are joined with one LF.

| Block | Exact composition |
| --- | --- |
| 0 | Leading 5-key Semantic-Discovery YAML frontmatter delimited by `---` lines (`FM-01`, `FM-02`): `title`, `description` (`>-` folded scalar, 60–140 whitespace-delimited words), `topics` (lowercase `kebab-case`), `use_when`, and conditional `not_for` (omitted when empty). |
| 1 | ATX H1 heading formed by `#`, one space, and the derived specification title (`catalog_name` plus `" specification"`, without duplicating `"specification"` when already present). |
| 2 | `## Identity and selection` |
| 3 | Six identity bullets under STR-02: `Specification ID` (`TYPE@variant` in code span followed by a period) and five labeled bullets (`Purpose`, `Intended readers`, `Decision or action supported`, `Use when`, `Scope boundaries`). |
| 4 | `## Authoring inputs and unresolved facts` |
| 5 | Inputs paragraph, any optional `notes` paragraphs, and unresolved-facts paragraph, each separated by one empty line under STR-03. |
| 6 | `## Finished-document contract` |
| 7 | Five contract bullets under STR-04 (`Title`, `Frontmatter`, `Client or receiving party`, `Order`, `Presentation`), using the deterministic `Frontmatter` template and fixed `Client or receiving party` constant. |
| 8 | Projection table under STR-05 using `\| --- \| --- \| --- \|`. |
| 9 | Role-table header, compact delimiter `\| --- \| --- \| --- \|`, and ordered pipe-delimited rows with one space around every cell under STR-06. |
| 10 | `## Content definitions and forms` |
| 11 | Element-table header, compact delimiter `\| --- \| --- \| --- \|`, and ordered pipe-delimited rows with one space around every cell under STR-08. |
| 12 | Forms paragraph under STR-09. |
| 13 | Optional supporting H3 blocks under STR-11 (`###` plus one space plus `heading`, followed by literal content block); omit when `supporting` is empty. |
| 14 | `## Quality criteria` |
| 15 | Ordered quality bullets under STR-10, each beginning with `-` and one space followed by `criterion.text`. |

The same `ready` request and project version define the same specification bytes. Acceptance gates verify actual output against this contract.

## Catalog integration

**CAT-01 — Tier-1 CSV catalog (`INDEX.csv`).** Maintain [INDEX.csv](INDEX.csv) at the repository root as the compact Tier-1 discovery catalog. Encode [INDEX.csv](INDEX.csv) as UTF-8 without BOM, comma-delimited RFC 4180 CSV with CRLF (`\r\n`) record terminators, double-quote quoting using minimal quoting (`QUOTE_MINIMAL`, doubled embedded quotes, no escape character), and the exact five-column lowercase `snake_case` header:

`family,type,title,path,summary`

- `family`: Registered family directory from [families.json](authoring/families.json).
- `type`: Unique specification ID (`TYPE@variant`).
- `title`: Human catalog name (`identity.catalog_name`), agreeing with the specification H1 and frontmatter `title` per STR-01.
- `path`: Repository-relative path (`family/lowercase(TYPE)--variant.spec.md`).
- `summary`: Concise, grounded one-line Tier-1 summary (`identity.catalog_summary`, 8–18 whitespace-delimited words, no trailing period).

**CAT-02 — Tier-2 derived JSON catalog (`CATALOG.json`) and deterministic ordering.** Maintain [CATALOG.json](CATALOG.json) at the repository root as the derived Tier-2 discovery index combining [families.json](authoring/families.json), [INDEX.csv](INDEX.csv) (`family`, `type`, `title`, `path`, `summary`), faceted frontmatter fields (`topics`, `use_when`, conditional `not_for`), and declared projection kinds (`standalone`, `native`) for single-read agent filtering (while full `description` summaries remain in each specification's leading YAML frontmatter). Encode [CATALOG.json](CATALOG.json) as UTF-8 without BOM, LF endings, 2-space indentation, and lexicographically sorted object keys at every nesting level. Order rows in [INDEX.csv](INDEX.csv) and entries in [CATALOG.json](CATALOG.json) deterministically by registered family order from [families.json](authoring/families.json) and then ascending ASCII `path` within each family. Templates and maintenance records under `authoring/` remain outside both catalogs.

**CAT-03 — Counts, version, and entrypoints.** Read registered directories from [families.json](authoring/families.json) and count actual `*.spec.md` files directly inside them. Detect unregistered specification directories and stop integration instead of silently excluding their files. Require exact 1:1 agreement among live `*.spec.md` files, [INDEX.csv](INDEX.csv) rows, [CATALOG.json](CATALOG.json) entries, unique IDs, and root-contained resolved paths. Update counts and the single project version across [README.md](README.md), [llms.txt](llms.txt), [CONTRIBUTING.md](CONTRIBUTING.md), [families.json](authoring/families.json), [request.template.json](authoring/request.template.json), [CATALOG.json](CATALOG.json), and [CHANGELOG.md](CHANGELOG.md). Record additions, revisions, refactorings, and removals directly under the new version heading in [CHANGELOG.md](CHANGELOG.md).

**CAT-04 — Scoped integration and sibling refactoring.** A specification addition updates the new specification file(s), [INDEX.csv](INDEX.csv), [CATALOG.json](CATALOG.json), entrypoint counts and version references, [CHANGELOG.md](CHANGELOG.md), and any existing sibling specifications whose scope boundaries or `not_for` exclusions require refactoring for catalog coherence.

## Authoring procedure and acceptance gates

**RUN-01 — Ordered procedure.** Perform these steps in order. On a failed gate, report the rule, affected ID or path, observed defect, and needed correction.

1. Establish scope, inspect scoped working-tree changes, read [README.md](README.md), [INDEX.csv](INDEX.csv), [CATALOG.json](CATALOG.json), this standard, registry, templates, and close specifications; check versions and paths.
1. Prepare the independent mission, source, task, and obligation inventory and unknown or exclusion rules under DES-01 and DES-02 before choosing family or literal composition. Then resolve reuse, addition or revision, complete variant, classification, and any sibling refactoring needed.
1. Design and review specification frontmatter, controlled and specific `topics`, catalog summary, obligations, conditions, cardinalities, states, finished-document frontmatter rules, projections, presentation, supporting content, source binding, and coverage. Evaluate ordinary, incomplete, and boundary finished instances under EVAL-01 and EVAL-02. Freeze literal text and change to `ready` only after required gates pass.
1. Compose under CMP-01 and CMP-02. Derive identities and paths under SEL-04.
1. Integrate [INDEX.csv](INDEX.csv), [CATALOG.json](CATALOG.json), entrypoint counts and project version, and [CHANGELOG.md](CHANGELOG.md) under CAT-01 through CAT-04.
1. Apply every acceptance gate below and verify actual outputs against this contract.

| Gate | Pass evidence | Failure treatment |
| --- | --- | --- |
| Input | Exact key and type checks; sorted JSON keys; ready; current library HEAD and working sources; registry version and digest; no template markers; valid identities, conditions, references, cardinalities, and revision bindings. | Stop composition; name the defect. |
| Frontmatter and purity | Specification YAML frontmatter validates against FM-01 (`title`, `description` 60–140 words, `topics` 3–12 lowercase `kebab-case` with 2–3 controlled tags, `use_when` 2–6, conditional `not_for` 1–5) and FM-02 (zero leaks, zero unresolved delimiters); finished-document contract requires compliant 5-key frontmatter on standalone GFM outputs. | Fix frontmatter metadata or contract wording and revalidate. |
| Mission coverage | Independent source and task inventory; applicable information maps to obligations, content, and observable cases; exclusions justified; unknowns and stopping rules visible. | Expose omitted information or missing source before composition. |
| Selection | Inspected comparisons establish reuse or a distinct purpose or applicability; family and variant rules are resolved; overlapping siblings are refactored cleanly. | Use the existing type or resolve the selection boundary. |
| Representation | Registered family; consistent 5-key frontmatter, title, syntax, metadata, snapshot, and authority rules for every supported projection; proportionate presentation and justified support. | Resolve conflict; do not force native data into an incompatible view. |
| Finished-instance use | Checked ordinary, incomplete, and relevant boundary cases including valid 5-key frontmatter; reader retrieves and uses necessary information; actual method, source, contract, and fixture bindings, outcomes, failures, and limits retained. | Keep required unresolved checks open; never substitute static inspection for execution. |
| Composition | Literal CMP-02 agreement; leading 5-key YAML frontmatter; exact title agreement with `INDEX.csv`; five H2s; six identity bullets; five contract bullets; projection, role, and element tables with compact `\| --- \|`; strict STR-06 status syntax; exact UTF-8 LF bytes. | Correct request or output and repeat. |
| Semantics | Roles, definitions, input requirements, condition predicates, states, forms, and quality coverage agree; claims and authority rules preserve TXT-02; no host-private coupling. | Identify contradictory or unsupported content. |
| Integration | Every live `*.spec.md` matches exactly one [INDEX.csv](INDEX.csv) row (RFC 4180 CRLF) and one [CATALOG.json](CATALOG.json) entry (sorted JSON LF); paths resolve; deterministic ordering; counts, single project version, and [CHANGELOG.md](CHANGELOG.md) match. | Correct catalog integration before reporting completion. |
| Compatibility | No missing-file links, broken anchors, or unintended changes appear in specifications or entrypoints. | Explain and correct unintended changes. |
