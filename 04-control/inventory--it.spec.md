# Observed IT inventory specification

## Identity and selection

- **Specification ID:** `INVENTORY@it`.
- **Purpose:** Record IT components or asset instances actually observed in a stated boundary, including the discovered attributes and the reconciliation status of that observation.
- **Intended readers:** Operators, support staff, security analysts, and configuration managers who need to know what was seen, when, and how it differs from a governed identity or approved baseline.
- **Decision or action supported:** Determine which components were observed or expected, what the collection could show, which owners or versions are still unknown, and which observations remain unreconciled.
- **Use when:** Operations, security, support, or configuration work needs a dated account of IT components actually observed and any reconciliation with supplied project records.
- **Scope boundaries:** Record collected observations and established reconciliation facts. Exclude desired-state definitions and administrative approval, acceptance, authorization, baseline-release, or disposal decisions.

## Authoring inputs and unresolved facts

Inspect the system or service boundary, the completeness definition, the collection or attestation methods that were actually authorized, their source revisions, the observation window, and what those methods cannot see. Inspect discovered identifiers, types, locations, versions, owners, and dependencies only as reported by those sources. Compare the observations with an asset registry, prior inventory, or approved baseline only when that record exists.

If an owner, version, location, or reconciliation result is unknown, record the component and the gap. Do not invent an asset identifier, a configuration fingerprint, a timezone, or a baseline difference. An expected component that was not seen is a `missing` entry only when the expectation comes from a named source. If a completed collection found no in-scope component, say so and describe the method and its limits. A document that describes no collection is not an inventory. Do not assign `pass`, `fail`, `inconclusive`, or `not-run`.

## Finished-document contract

- **Title:** Identify the system or service boundary and name the document as its observed IT inventory, including the observation as-of point.
- **Frontmatter:** None. Begin with the GFM title. Collection limits, observation times, and reconciliation status belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the boundary, collection, and reconciliation rules before the entries; place unresolved discrepancies after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Boundary, collection, and refresh | Required | Identify the system or service scope, accountable owner, completeness definition, and exclusions. Describe each authorized discovery or attestation method, its source revision, observation window, and blind spots. State the project's review interval and change triggers.  |
| Reconciliation rules | Required | State how duplicates, unrecognized components, unknown owners, and expected-but-absent components are handled. Compare with an approved baseline or asset registry only when that record was identified; otherwise state that the comparison was not performed. Keep discovered attributes separate from identifiers or approved revisions obtained through comparison. A comparison records correspondence and discrepancies; it grants no approval, baseline release, or authorization. |
| Observed entries | Required | Include one entry for each observed instance and for each expected instance this collection accounts for as missing, or an explicit statement that the completed collection found none. Record only attributes the source reported, the observation time, and the reconciliation facts that exist. |
| Open discrepancies | Required | List duplicate identities, unknown owners, unobserved versions or locations, unmatched components, and comparisons not yet performed, each with its consequence, or state that the assessed collection left none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Inventory entry | One distinct component instance in this account. | Keep the entry identifier stable for that instance and do not reuse it for a different instance. Do not merge two instances because they share a product name. Within one inventory, a later observation of the same instance updates that entry and keeps a material conflict visible. A separate point-in-time inventory may assign its own entry identifiers. |
| Asset reference | Required to address for each entry. | Cite a real asset-registry identifier when the instance is registered. Otherwise state that it is unregistered or that registration was not established. Do not invent an asset identity, and do not treat this inventory identifier as that asset identity. |
| Observed component identity | One identifier and its issuing source for each seen instance. | For a `missing` entry, give the expected identifier and the named source of the expectation. The inventory entry identifier and the source-system identifier may differ; do not collapse them silently. |
| Component type | One type per entry. | Use the observed class, including hardware, software, or service when that is what was seen. If the source did not establish the type, record it as unknown. |
| Owner | Required to address for each entry. | Name the accountable owner when established. An unknown owner is an open issue, not a role to invent. |
| Location | The physical or logical location and system association reported by the source. | If the collection did not observe location, say so. Do not copy governed custody from an asset registry as if it had been discovered. |
| Version and configuration | Only the version, patch level, or configuration fingerprint the source reported. | If the source omitted them, record that they were not observed. Do not synthesize a hash or patch level. |
| Collection source | One discovery or attestation source per entry. | Name the method and the authority for using it. A planned method is not an observation. |
| Dependencies | Zero or more links to other entries in this inventory. | Include a dependency only when the stated source observed or reported it. Each linked entry must retain its own observation or named expectation basis. |
| Criticality | Exactly one of `unassessed`, `low`, `moderate`, `high`, or `critical`. | Define the project criteria before using any value other than `unassessed`. Criticality is not an authorization. |
| Observation status | Exactly one of `observed`, `confirmed`, `missing`, `unauthorized`, or `retired`. | `observed` means seen and not yet matched. `confirmed` means matched to a named governed or expected identity. `missing` means a named expectation was not seen. `unauthorized` means a comparison found no matching governed identity or approved baseline; it is not an authorization decision and MUST NOT be used when no comparison was made. `retired` means the instance was determined to be no longer present, with the basis. These labels describe observation and reconciliation. They grant no configuration-control approval, baseline release, or operational authorization and do not change asset lifecycle or disposal state. Do not assign `pass`, `fail`, `inconclusive`, or `not-run`. |
| Observation time | One time per entry. | Use a date-time with a timezone when the source provides one. If the source time is date-only or lacks a zone, record that limitation instead of inventing an offset. |
| Reconciliation time and evidence | Required to address for each entry. | Record the reconciliation time only when reconciliation occurred. State what was compared, the discrepancies, and who resolved them, or state that reconciliation is not established and why. Resolving a discrepancy does not release a baseline, authorize the component, or change asset lifecycle state. |

Use one row per instance. Put attributes the collection could not see in the discrepancy section rather than in fabricated cells. Every row must identify an observed instance or a sourced missing instance; comparison data must be labeled separately from observed attributes.

## Quality criteria

- Every entry comes from a stated collection or from a named expectation that explains a missing component.
- Observed attributes, governed asset identity, approved baseline revisions, and authorization decisions remain distinct.
- Unknown owners, versions, locations, and timezones stay unresolved rather than being completed from another record.
- A ranked criticality has project criteria, and `unauthorized` has a real comparison. Neither is authorization or baseline release.
- It assigns no `pass`, `fail`, `inconclusive`, or `not-run`.
