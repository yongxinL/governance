# Central Governance Reference

| Field | Value |
|---|---|
| Governance | Nexora Governance |
| Governance repository | `<GOVERNANCE_REPOSITORY_URL>` |
| Adopted version | `1.0.1` |
| Release tag | `v1.0.1` |
| Verified package identity | `MANIFEST.json` SHA-256 for every file except itself |
| Adoption record | `docs/governance/governance-adoption.md` |
| Project owner | `<PROJECT_OWNER>` |
| Upgrade review status | Not yet reviewed for this release |

The governance repository location is a required project input supplied by the
Project Owner. This scaffold ships no default repository URL because that value
is deployment-specific. Replace `<GOVERNANCE_REPOSITORY_URL>` only with the real
location; never invent one.

## Authority

This project is governed by the Nexora Governance release identified above. The
central manual at that release is authoritative for governance rules; this file
is a pointer and does not copy them.

This scaffold identifies governance release `1.0.1` and release tag `v1.0.1`.
Verify the exact central release and package integrity before recording the
adopted immutable tag.

## Verified baseline of the previous release

The `1.0.0` release was declared Released on 2026-10-12 at source baseline commit
`d00dcab5f70c083a37d612e48eacb67e38aa272e`. No local or origin `v1.0.0` tag was
found. Do not record `v1.0.0` as an immutable reference: a missing tag does not
invalidate the release declaration, and this scaffold does not create a
retrospective tag.

## Upgrade rule

This project does not follow the central default branch. Upgrades are reviewed
and adopted explicitly, and both this file and
`docs/governance/governance-adoption.md` are updated in the same commit.

## Exceptions

Project exceptions are recorded in
[docs/governance/documentation-exceptions.md](docs/governance/documentation-exceptions.md)
and cannot waive the central non-exception controls (NX-1 through NX-6).

## Project records

- [Governance adoption](docs/governance/governance-adoption.md)
- [Source-of-truth register](docs/governance/source-of-truth-register.md)
- [Approved tooling](docs/governance/approved-tooling.md)
- [Tooling adoption register](docs/governance/tooling-adoption-register.md)
