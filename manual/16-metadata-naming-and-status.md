# 16. Metadata, Naming, and Status

**Part IV** · **Owns:** minimal metadata, identifiers, number allocation, dates, filenames, owner role, controlled statuses, status transitions, historical identifiers.

## 16.1 Minimal metadata

Governed Nexora artifacts begin with a metadata table or YAML front matter containing:

| Field | Required | Notes |
|---|---|---|
| `id` | Where the type has an identifier | For example `ADR-007` |
| `title` | Yes | |
| `status` | Yes | Controlled vocabulary (16.6) |
| `owner` | Yes | `project-owner` when the owner is named centrally |
| `created` | Yes | `YYYY-MM-DD` |
| `updated` | Yes | `YYYY-MM-DD` |
| `approved_by`, `approval_mode`, `approved_on` | When approved | See [chapter 05](05-lifecycle-ownership-and-approvals.md) |
| `supersedes`, `superseded_by` | When applicable | Identifier references |

Native Spec Kit artifacts keep their native structure; record `SPEC-NNN`, status, and approval fields inside the specification content in a compatible way (for example a short metadata block below the title).

## 16.2 Identifiers

| Type | Format | Example |
|---|---|---|
| Specification | `SPEC-NNN` | `SPEC-004` |
| Functional requirement | `SPEC-NNN-FR-NNN` | `SPEC-004-FR-002` |
| Non-functional requirement | `SPEC-NNN-NFR-NNN` | `SPEC-004-NFR-001` |
| Acceptance criterion | `SPEC-NNN-AC-NNN` | `SPEC-004-AC-003` |
| ADR | `ADR-NNN` | `ADR-012` |
| RFC | `RFC-NNN` | `RFC-003` |
| Investigation | `INV-NNN` | `INV-009` |
| Lesson | `LES-NNN` | `LES-002` |

Examples in this manual are illustrative and do not refer to real artifacts. Do not create identifiers for document types without a governance purpose.

### 16.2.1 Project-local exception labels

`EXC-NNN` is a **project-local** register label used in each project's
`docs/governance/documentation-exceptions.md`. It is not one of the centrally
allocated identifier families in 16.2, and the central package does not allocate,
reserve, or audit exception numbers across projects. Allocation, non-reuse, and
retention of `EXC-NNN` are owned by the project's exception register under
[chapter 04](04-governance-versioning-and-exceptions.md#43-exception-types).

This distinction is recorded deliberately. Earlier drafts of this chapter listed
`EXC-NNN` alongside the centrally allocated families while defining no central
allocation rule for it, which implied a central obligation that no other chapter
established. Removing it from 16.2 resolves that inconsistency without changing
existing project behaviour.

### 16.2.2 Decision records: D1-D20 and DEC-001 through DEC-020

Two decision-naming conventions exist and must not be merged or renumbered:

- `D1` through `D20` are the labels of the approved v1.0 governance decisions.
  They are historical references, not an allocatable identifier family.
- `DEC-001` through `DEC-020` are maintenance decision records under
  `maintenance/decisions/`. Per `maintenance/README.md`, they correspond to the
  approved v1.0 decisions D1-D20.

`DEC-NNN` is maintained by the central repository, not by adopting projects.
Projects do not allocate `DEC-NNN` values and must not copy central decision
records into `docs/`. Central decisions are repository-only and are outside the
released package.

**OWNER_DECISION:** the `maintenance/decisions/` directory does not yet exist in
this repository. Whether it should be created, and whether `D1`-`D20` remain
only as historical aliases or are formally superseded by `DEC-001`-`DEC-020`, is
unresolved. This chapter preserves both conventions and asserts no supersession.
Resolving it changes no adopting project's obligations either way.

## 16.3 Allocation

- Allocated per project, sequentially, three digits minimum (expand to four when needed).
- Allocated in the area index at creation; the index is authoritative for allocation.
- Never reused. Gaps are acceptable.
- Identifiers survive title and path changes.
- Withdrawn, rejected, cancelled, deprecated, and superseded identifiers remain listed in the index.
- Spec Kit's native feature numbering may differ from `SPEC-NNN`; align where practical, otherwise the index maps them.

## 16.4 Dates

`YYYY-MM-DD`. Use full ISO 8601 timestamps with offset only where time matters (incidents, releases, handoffs).

## 16.5 Filenames

Lowercase kebab-case. Governed types prefix the identifier: `ADR-NNN-<title>.md`, `RFC-NNN-<title>.md`, `INV-NNN-<title>.md`, `LES-NNN-<title>.md`. Release records use the version. Native Spec Kit names stay native.

## 16.6 Controlled statuses

| Type | Statuses |
|---|---|
| Specification | Draft, In Review, Approved, In Implementation, Implemented, Verified, Superseded, Withdrawn |
| RFC | Draft, In Review, Accepted, Rejected, Deferred, Withdrawn, Superseded |
| ADR | Proposed, Accepted, Deprecated, Superseded, Rejected |
| Investigation | Planned, In Progress, Completed, Cancelled, Superseded |
| Release | Planned, Candidate, Released, Withdrawn, Superseded |
| Lesson | Draft, Accepted, Incorporated, Retired |

Cross-specification delivery plans use the specification vocabulary. Test plans and runbooks use Draft, Approved, Superseded. Product documents use Draft, In Review, Approved, Superseded.

Approved, Accepted, Implemented, Verified, and Released are distinct states and are never interchangeable.

## 16.7 Transitions

Material transitions are owner-controlled ([chapter 05](05-lifecycle-ownership-and-approvals.md#58-status-transitions)). Every transition updates both the artifact and its index entry in the same commit.

## 16.8 Owner role

Use `owner: project-owner`. Name individuals only in `governance-adoption.md` (and in role tables under collaborative mode).
