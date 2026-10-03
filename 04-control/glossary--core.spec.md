# Concept-oriented glossary specification

## Identity and selection

- **Specification ID:** `GLOSSARY@core`.
- **Purpose:** Control the shared meanings of project or domain concepts, including each concept's preferred designations, permitted and deprecated aliases, sources, and distinctions.
- **Intended readers:** Authors and reviewers who must use the same meanings across project documents, and the role that stewards the vocabulary.
- **Decision or action supported:** A reader can tell which designation to use, what the concept means in this subject field, which designations are deprecated, and whether the definition was adopted, adapted, or written for the project.
- **Use when:** Project or domain terms, acronyms, meanings, aliases, sources, and distinctions need one controlled vocabulary shared across documents.
- **Scope boundaries:** Entries define concepts and their designations within the stated subject field and languages. An acronym expansion alone is insufficient without a definition of the underlying concept. Adoption records the vocabulary decision for that entry.

## Authoring inputs and unresolved facts

Obtain the subject field, the audiences, each language in scope, and any naming convention the project actually uses. Obtain the steward role and the rule for adopting or changing a concept, or record that either is unassigned. Obtain each concept the project needs to control: its preferred designation in each declared language, the definition that distinguishes it, the context in which that meaning applies, whether the definition was adopted, adapted, or written for the project, and the supplied definition source, version, locator, and reuse permission or paraphrase basis that support that choice. Obtain permitted aliases, deprecated designations, and relations to other concepts only when they exist.

If the subject field or language is unknown, say so and leave it unresolved. If the steward or adoption rule is not established, mark every entry proposed and keep the document from being presented as the adopted vocabulary. If a concept, definition, source version, or reuse permission is unknown, record that gap on the entry. Do not invent a term, definition, version, license, or related concept. If no concept has been established, say that the controlled vocabulary is not established and add no placeholder concept. Absence of entries leaves the question of further terms open. Do not copy source text verbatim unless the entry states a redistribution permission the project actually holds. A source name alone does not identify the version supporting the entry.

## Finished-document contract

- **Title:** Name the subject field and identify the document as its concept glossary.
- **Frontmatter:** None. Begin with the GFM title. Scope, designations, and definitions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give scope and stewardship before the entries. Present unresolved disputes with or after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and stewardship | Required | State the subject field, audiences, each language in scope or the unresolved language, and any naming convention actually in use. Name the steward role or the assignment gap. State the adoption and change rule, or that it is not established. Identify each vocabulary supplying definitions used by the project, with its supplied version, or state that no such vocabulary is used. State the order used to find an entry. |
| Concept entries | Required | Record each established concept once, with a stable ID, preferred designation, distinguishing definition, subject context, definition origin, and source and rights. Include permitted and deprecated designations and related concepts only when they exist. If no concept is established, state that limit instead of a placeholder entry, and do not call the document the controlled vocabulary. |
| Unresolved disputes | Required | State each recorded conflict between meanings, designations, or sources, and any steward selection among them. If none are recorded, say so. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Concept entry | One per concept the project has established. Zero only when the document states that no concept is established; that document is not the controlled vocabulary. | Keep one entry for one concept, including when the concept has an acronym. Use two entries when one designation carries two meanings. |
| Concept ID | One per entry, stable across revisions of that concept. | Never reuse an ID for a different concept. Follow a project identifier scheme when one exists. Do not add a second identifier to satisfy a character pattern. |
| Preferred designation | One per declared language for each entry, or an explicit gap for a language whose designation is not established. | The designation is the term, symbol, or name to use. An acronym is the preferred designation only when the entry also gives the full form, or states that the acronym is the name in use. |
| Permitted designation | Zero or more per entry. | Each item is a synonym, abbreviation, or other alias of the same concept, with the context in which it is permitted. An expansion list without a concept definition is not an entry. |
| Deprecated designation | Zero or more per entry. | Each item names a designation the vocabulary discourages and the designation to use instead. Deprecation keeps the same concept. |
| Definition | One per entry. | State the meaning in the subject context and distinguish it from the related concepts named on the entry. Give the concept its own meaning rather than only repeating the preferred designation or only pointing at another entry. Express the concept's meaning rather than an instruction to perform an action. |
| Subject context | One per entry. | State the field or situation in which this meaning applies. The same designation in two contexts is two entries. |
| Definition origin | One per entry, or an explicit unresolved origin. | Use `adopted` only when the definition matches the supplied source definition and source and rights state the redistribution permission relied on. Use `adapted` when a supplied source definition was changed, including a paraphrase, and state the change. Use `project-specific` when the definition was written for this scope. Leave the origin unresolved when the source definition or version is unavailable. |
| Source and rights | One per entry. | For an adopted or adapted definition, give the exact supplied source, version, and locator, plus the redistribution permission relied on or the paraphrase basis. For a project-specific definition, state that it was written for this scope and identify any source idea that was paraphrased. Do not invent a license. |
| Usage note | Conditional on a usage limit, illustration, or cross-reference that the definition does not already state. | Label an illustration as an illustration. A project fact in a note must be a real fact. An empty note does not record a dispute. |
| Related concept | Zero or more per entry. | Each link names another entry in this glossary, or an external concept whose source already exists, and states whether the relation is broader, narrower, or associated. Do not invent an ID for a concept that is outside this glossary. |
| Dispute | Zero or more for the document. | Name the concept, the competing meanings or sources, and the steward's selection when one exists. State that none are recorded only after looking for them. |
| Finding order | One for the document. | Alphabetical order by preferred designation in a declared language is the normal choice. Another order needs a reason a reader can use to find a term. |

Use a glossary table or a definition list that shows the preferred designation, definition, origin, and any permitted or deprecated designations. Use short prose where a distinction, rights limit, or dispute would be ambiguous in a cell. Do not include blank rows, a generic document-lifecycle block, a synthetic-data flag, or an imposed approval signature.

## Quality criteria

- Every entry is one concept, and every designation on that entry points at that concept.
- Preferred, permitted, and deprecated designations are distinguishable, and a deprecated designation says what to use instead.
- The same preferred designation is not used for two concepts in the same language and context.
- Each definition distinguishes the concept from the related concepts the entry names and expresses its meaning without prescribing an action.
- Origin, supplied source version, and reuse permission agree. An unavailable source definition or version, or a definition without established redistribution permission, is not marked `adopted`.
- Entries stay proposed while the steward or adoption rule is unestablished. A document with no established concepts does not claim to be the shared vocabulary.
- Recorded disputes are visible. 
