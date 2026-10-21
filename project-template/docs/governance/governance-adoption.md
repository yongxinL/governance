# Governance Adoption Record

| Field | Value |
|---|---|
| Project name | `<PROJECT_NAME>` |
| Project Owner | `<PROJECT_OWNER>` |
| Governance mode | `solo` |
| Central repository | `<GOVERNANCE_REPOSITORY_URL>` |
| Scaffold source version | 1.0.1 |
| Release tag | `v1.0.1` |
| Adopted version | `<ADOPTED_VERSION>` |
| Adopted immutable tag | `<ADOPTED_TAG>` |
| Scaffold initialization date | `<SCAFFOLD_INITIALIZED_DATE>` |
| Adoption review date | `<ADOPTION_REVIEW_DATE>` |
| Adoption date | `<ADOPTION_DATE>` |
| Adoption state | Adoption in Progress |
| Primary agent | `<PRIMARY_AGENT>` |
| Active Spec Kit integration | `<SPEC_KIT_INTEGRATION_KEY>` |
| Exceptions location | [documentation-exceptions.md](documentation-exceptions.md) |
| Tooling register | [tooling-adoption-register.md](tooling-adoption-register.md) |
| Maturity target (optional) | Level 1: Controlled |

## Lifecycle distinctions

These are separate events and must not be collapsed into one date or one approval:

- **Scaffold initialization:** the scaffold was copied into this repository. This
  is a file-copy fact, not an approval.
- **Adoption review:** the mandatory controls were assessed, for example by
  prompt 04. This is a recommendation.
- **Project Owner approval:** the owner approved adoption. Only this event is an
  approval, and only this event sets the adoption state to `Adopted`.
- **Adoption completion:** validation passed and the state was committed.
- **Governance upgrade:** a later adoption of a different central release.

A scaffold initialization date is never an adoption approval date. An adoption
review is never an approval. This record must not be pre-populated with an
approver, an approval mode, an approval date, or completed validation evidence.

The rows above describe the package this scaffold was copied **from**. Record
`<ADOPTED_VERSION>` and `<ADOPTED_TAG>` only after verifying the exact release
and its package integrity.

## Previous release baseline

The `1.0.0` release was declared Released on 2026-10-12 at source baseline commit
`d00dcab5f70c083a37d612e48eacb67e38aa272e`. No local or origin `v1.0.0` tag was
found, so `v1.0.0` must not be recorded as an immutable adopted tag.

## Review triggers

Review this record on: governance upgrade, ownership change, contributor-access change, primary-agent or integration change, external exposure change, significant incident, major risk change, and project retirement.

## Adoption history

| Date | Version | Tag | State | Approval mode | Baseline commit |
|---|---|---|---|---|---|
| `<ADOPTION_DATE>` | `<ADOPTED_VERSION>` | `<ADOPTED_TAG>` | Adoption in Progress | Pending | Recorded after the adoption commit |

## Notes

Record here any customization marker that cannot yet be resolved and why. Remove resolved notes.
