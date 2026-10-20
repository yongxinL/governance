# Version

| Field | Value |
|---|---|
| Governance name | Nexora Governance |
| Version | 1.0.0 |
| Release tag | `v1.0.0` |
| Release status | Released |
| Release date | 2026-10-12 |
| Tooling guidance verified | 2026-10-12 |

## Versioning policy summary

Nexora Governance uses semantic versioning based on governance impact, as owned by [manual chapter 04](manual/04-governance-versioning-and-exceptions.md):

- **Patch (1.0.x):** corrections, clarifications, link repair, non-material wording, example or generated-file corrections. No new mandatory obligation.
- **Minor (1.x.0):** backward-compatible improvements, new optional templates, newly approved capabilities, improved validation, additional optional tooling guidance.
- **Major (x.0.0):** source-of-truth, workflow-owner, identifier-meaning, mandatory-structure, mandatory-approval, or artifact-authority changes.

## Compatibility and adoption notes

- Projects adopt this release explicitly by recording repository, version `1.0.0`, and tag `v1.0.0` in `docs/governance/governance-adoption.md`.
- Projects never track the central default branch.
- Governance policy in this release is stable. Version-sensitive tool procedures (Spec Kit, OpenCode v2, Codex, MCP servers) were verified on 2026-10-12 and must be re-verified against the pinned tool version during adoption; differences in tool syntax are corrected through a patch release, not by changing governance policy.
- OpenCode guidance targets the OpenCode v2 configuration format.
