# Version

| Field | Value |
|---|---|
| Governance name | Nexora Governance |
| Version | 1.0.1 |
| Planned release tag | `v1.0.1` |
| Release status | Draft for release |
| Release date | Pending |
| Tooling guidance verified | 2026-10-12 |

The `v1.0.1` tag does not exist yet. This file records release intent, not a
published release.

## Verified 1.0.0 baseline

| Field | Value |
|---|---|
| Verified 1.0.0 source baseline | `d00dcab5f70c083a37d612e48eacb67e38aa272e` |
| 1.0.0 declaration date | 2026-10-12 |
| Local `v1.0.0` tag | Not found |
| Origin `v1.0.0` tag | Not found |

`VERSION.md` at the baseline commit declared version `1.0.0`, tag `v1.0.0`,
status `Released`, and release date `2026-10-12`. No `v1.0.0` tag was found in
the local repository or on `origin`. This release records that gap truthfully
and does not create a retrospective tag. Whether to create one is a separate
Project Owner decision outside the scope of this release.

## Versioning policy summary

Nexora Governance uses semantic versioning based on governance impact, as owned by [manual chapter 04](manual/04-governance-versioning-and-exceptions.md):

- **Patch (1.0.x):** corrections, clarifications, link repair, non-material wording, example or generated-file corrections. No new mandatory obligation.
- **Minor (1.x.0):** backward-compatible improvements, new optional templates, newly approved capabilities, improved validation, additional optional tooling guidance.
- **Major (x.0.0):** source-of-truth, workflow-owner, identifier-meaning, mandatory-structure, mandatory-approval, or artifact-authority changes.

## Release-classification exception

The Project Owner approved shipping the `v1.0.1` corrective documentation scope
under a patch version. Part of that scope would ordinarily be classified as
minor under the policy above, because it adds optional, backward-compatible
material.

This is recorded as an explicit owner-approved compatibility exception. It does
not alter the classification policy itself, does not create a new mandatory
obligation for adopting projects, and does not change source-of-truth ownership,
workflow ownership, identifier meaning, mandatory approvals, or native GitHub
Spec Kit ownership.

## Compatibility and adoption notes

- Projects adopt this release explicitly by recording repository, version `1.0.1`, and planned tag `v1.0.1` in `docs/governance/governance-adoption.md`.
- Projects never track the central default branch.
- A project already adopted on `1.0.0` requires no migration. The corrections in
  this release are documentation corrections and clarifications, not changes to
  a project's governance obligations.
- Governance policy in this release is stable. Version-sensitive tool procedures (Spec Kit, OpenCode v2, Codex, MCP servers) were verified on 2026-10-12 and must be re-verified against the pinned tool version during adoption; differences in tool syntax are corrected through a patch release, not by changing governance policy.
- OpenCode guidance targets the OpenCode v2 configuration format.
