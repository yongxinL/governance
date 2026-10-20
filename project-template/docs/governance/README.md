# Project Governance

This directory contains project-specific governance records. It does not copy
the central governance manual.

| Record | Authority |
|---|---|
| `governance-adoption.md` | Adopted release, owner, mode, state, primary agent, and active integration |
| `source-of-truth-register.md` | One authoritative location per information category |
| `approved-tooling.md` | Tools permitted for project use |
| `tooling-adoption-register.md` | Actual tool lifecycle and configuration state |
| `documentation-exceptions.md` | Temporary and standing project exceptions |

Material changes require Project Owner review. NX-1 through NX-6 cannot be
waived by ordinary exceptions.

## Relationship to the central release

These records specialize the adopted central release. They must not weaken,
override, or contradict it. Where a record and the central manual appear to
disagree, the central manual governs and the discrepancy is a finding to resolve.

## Artifact triggers

| Record | Update trigger |
|---|---|
| `governance-adoption.md` | Initial adoption, governance upgrade, owner or mode change, primary-agent or integration change, adoption-state transition |
| `source-of-truth-register.md` | A category's authoritative location changes, or a new governed category appears |
| `approved-tooling.md` | A tool permission is granted, restricted, or prohibited; on any review trigger |
| `tooling-adoption-register.md` | A tool is planned, piloted, enabled, disabled, or removed |
| `documentation-exceptions.md` | An exception is raised, reviewed, resolved, or withdrawn |

## Index fields

This index records the governed records in this area. Each record carries its own
metadata: state, owner, dates, and its own authority statement.

## Truthful empty state

Before adoption customization is complete, these files are scaffolds containing
unresolved markers. That is the truthful state and is not a defect. The presence
of these files does not mean the project has adopted governance; only a recorded
Project Owner approval in `governance-adoption.md` does.

No exception has been recorded until one is actually written and approved. An
empty exception register is a correct empty state, not a missing artifact.
