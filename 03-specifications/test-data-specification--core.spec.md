# Test data specification

## Identity and selection

- **Specification ID:** `TEST-DATA-SPECIFICATION@core`.
- **Purpose:** Define reproducible test inputs or datasets, their expected properties, provenance, allowed use, protection, and lifecycle for a bounded set of tests.
- **Intended readers:** Test designers and operators, data owners and stewards, environment owners, security or privacy reviewers, and people interpreting test results.
- **Decision or action supported:** Select or generate suitable data, prepare it safely for the intended tests, verify its properties, and identify limitations that affect coverage or result interpretation.
- **Use when:** Test inputs or datasets need controlled definition beyond the values in a single test case, especially when provenance, representativeness, reproducibility, sensitivity, or reuse matters.
- **Scope boundaries:** Specify logical data assets and reproducible selection or generation rules for the stated tests. Identify materialized snapshots or generated instances only when established, with their actual editions, locators, and observed properties.

## Authoring inputs and unresolved facts

Obtain the test objectives and conditions, required input classes and edge cases, data structures and validity rules, sources or generator behavior, relevant versions, volume and distribution needs, expected known properties, handling constraints, allowed use and rights, and lifecycle requirements. Inspect how data will be identified at execution, reproduced or regenerated, checked before use, isolated between tests, refreshed, retained, and disposed of. For sensitive or production-derived data, obtain the actual data-owner and project handling decisions before asserting permitted use.

If a source, use right, sensitivity classification, schema, generation parameter, expected property, or retention rule is unknown or undecided, identify the affected data asset, effect on test suitability or authorized use, resolving action, and actual owner if assigned. A planned asset may be specified before materialization, but its locator, version, checks, and availability must remain visibly unresolved until established. A claim that a particular run loaded a materialized snapshot or generated instance requires an observation identifying that actual edition. Do not label materialized data as valid, synthetic, anonymized, licensed, or authorized without evidence for the relevant claim. Do not place actual personal data, credentials, secrets, or protected sample records in the document merely to describe them.

## Finished-document contract

- **Title:** Name the test effort or data scope and the document as its test data specification; distinguish an applicable edition when needed.
- **Frontmatter:** None. Begin with the GFM title. Data definition, provenance, and use constraints are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State test need and selection rules before individual assets; state protection and lifecycle rules before any claim that data is ready for use. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and selection model | Required | Identify the tests or conditions served, relevant item configuration, data classes, normal and boundary values, invalid inputs when needed, representativeness or sampling rationale, exclusions, and known limits. Distinguish designed coverage from actual use in a run. |
| Data asset definitions | Required | Define one or more distinct datasets, input collections, or generator recipes. For each, give identity, source or generation rule, reproducible edition or snapshot rule, format and schema, meaningful value constraints and expected properties, intended conditions, and availability or unresolved state. |
| Provenance and permitted use | Required | State origin, ownership or source, acquisition or generation method, applicable rights and use restrictions, and handling decision for each asset. Give generation parameters, seed, or source edition where needed for reproduction. State when production-derived data is prohibited or conditionally authorized. |
| Protection and lifecycle | Required | Define classification or sensitivity where relevant, minimization, masking or synthetic generation rules, access and transfer limits, storage, isolation between tests, refresh or mutation control, retention, and disposal appropriate to the data. State who controls consequential changes. |
| Data suitability checks and limitations | Required | Specify how structure, valid and invalid ranges, distribution or boundary coverage, integrity, and expected known properties will be checked before use. State unresolved checks, material biases, and how a changed asset or failed check affects test use. Report actual check outcomes only when observed, with evidence and edition. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Test condition and data need | One or more mappings from intended tests to needed data classes or properties. | Identify the relevant condition or case when established. Explain why each distribution, boundary, invalid input, or known-answer property matters; do not force all classes into every asset. |
| Data asset | One or more distinguishable datasets, collections, or generator recipes. | Assign a stable local or project identity. Distinguish a logical data definition from a materialized snapshot or generated instance; a planned asset need not pretend to have a real hash or location. |
| Reproduction rule | One per asset, complete enough to identify or recreate the edition used. | Give an immutable snapshot/version or source edition and generator instructions with parameters and seed where applicable. Use a content digest or other integrity identifier when the project relies on exact bytes; do not mandate a hash for data that is defined by controlled generation and checked properties. Label planned digest and generation rules as planned; identify an actual digest, generated instance, or run use only from observations bound to the materialized edition. |
| Schema and validity rule | One account per asset of relevant fields, types, units, ranges, relationships, and valid or deliberately invalid forms. | Identify schema or format edition where applicable. State constraints at the level needed to prepare and check the data; a generic format name alone is insufficient when value semantics affect testing. |
| Expected property | One or more properties per asset that matter to the intended tests. | Define expected distribution, class balance, boundary coverage, reference value, or known error case as applicable and how it will be checked. A property of input data is not a claim that the system under test passed. |
| Provenance and rights | One account per asset. | Identify origin, actual owner or supplier where known, source or generator, applicable license or consent/use decision when relevant, and restrictions on copying or disclosure. A URL or filename alone is not a rights decision. |
| Protection and lifecycle rule | One coherent rule set for each relevant sensitivity or use class. | State permitted users and environment, preparation or deidentification, storage and transfer, retention or deletion, and reset or refresh where needed. Do not claim data is anonymous because identifiers were merely masked. |
| Suitability check | One or more assessable checks for each asset's material properties. | State expected outcome and method or evidence basis. If an actual check is reported, bind its result to the asset edition and observation; otherwise call it a planned check. Limit each reported conclusion to the data properties actually checked. A claim of run use requires an observation identifying the loaded edition. |

Use prose for selection rationale, provenance, and limits. A table is suitable for asset identity, source or generator, edition, schema, expected properties, sensitivity, intended conditions, and checks when several assets exist. A compact field or value-range table MAY define a complex schema. Do not embed protected records, blank asset rows, or test-case execution steps.

## Quality criteria

- Each asset's definition, source, edition or generation rule, schema, and expected properties are sufficient to select or reproduce data at the precision the tests require.
- Mappings show why the data covers the intended conditions and make omissions, sample bias, and invalid-input needs visible.
- Provenance, rights, sensitivity, access, and lifecycle rules agree; an unresolved permission or protection rule blocks a claim that the data is ready for use.
- Suitability checks are tied to the actual asset edition, and planned checks are not reported as observed validity or test success.
- Each asset states the data properties, use conditions, and handling rules needed for its intended tests.
- Any claim of materialization or run use identifies the actual edition and supporting observation; reproduction rules and suitability findings retain their stated scope.
