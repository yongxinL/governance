# 17. Indexing, Traceability, and Source of Truth

**Part IV** · Owns: distributed indexes, source-of-truth register, index authority, linked-artifact authority, forward and backward traceability, native Spec Kit traceability, optional matrices, stable links, orphan classification.

## 17.1 Distributed indexes

Each documentation area has a README index: `docs/README.md`, `docs/governance/README.md`, `docs/product/README.md`, `docs/architecture/README.md`, `docs/architecture/adr/README.md`, `docs/rfc/README.md`, `docs/investigations/README.md`, `docs/testing/README.md`, `docs/operations/README.md`, `docs/operations/runbooks/README.md`, `docs/releases/README.md`, `docs/lessons/README.md`, `docs/archive/README.md`, `docs/templates/README.md`.

After Spec Kit initialization, `specs/README.md` indexes specifications, **only if** the installed version tolerates a non-feature file in `specs/` (verify that native scripts that enumerate `specs/*/` are unaffected). If not, record the specification index in `docs/README.md` under a "Specifications" section and note the reason in `documentation-exceptions.md`.

## 17.2 Index entry

| Column | Content |
|---|---|
| ID | Identifier |
| Title | Linked to the artifact |
| Status | Controlled status |
| Updated | Date |
| Baseline | Commit or tag of the approval or current baseline, where applicable |
| Relations | Supersedes or superseded by, related IDs |

## 17.3 Authority split

- **Indexes are authoritative for:** identity, identifier allocation, location, status, supersession, baseline reference.
- **Linked artifacts are authoritative for:** complete requirements, decisions, rationale, procedures, evidence, acceptance criteria.

If an index and an artifact disagree on status, treat it as a finding and correct both in one commit after owner confirmation.

## 17.4 Source-of-truth register

`docs/governance/source-of-truth-register.md` maps each information category to one authoritative location and names supporting locations. It is consulted before creating any document and updated when a category's location changes.

## 17.5 Traceability

- **Forward:** product requirement -> SPEC -> FR/NFR/AC -> native plan -> native tasks -> tests and evidence -> release record.
- **Backward:** release -> SPEC baselines -> AC -> evidence; code change -> task -> requirement.
- **Native:** use Spec Kit's own references between spec, plan, and tasks, and its analysis command, as the primary traceability mechanism.

## 17.6 Optional consolidated matrix

No universal traceability matrix is required. Introduce one (in `docs/testing/`) only for cross-feature complexity, cross-project requirements, release complexity, external obligations, or repeated audit difficulty.

## 17.7 Links

Use repository-relative links inside a project. Reference central governance by repository URL and immutable tag, never by default branch.

## 17.8 Orphan classification

| Class | Meaning | Action |
|---|---|---|
| Unindexed governed artifact | Exists but missing from its index | Add to index |
| Broken index entry | Index points to nothing | Restore or mark withdrawn with explanation |
| Unowned document | No clear category | Classify via the source-of-truth register |
| Legacy document | Pre-adoption content | Handle through migration ([chapter 28](28-archive-retention-and-migration.md)) |
