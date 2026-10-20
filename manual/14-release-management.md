# 14. Release Management

**Part III** · Owns: release records, release status, source baseline, specification baselines, verification references, migrations, compatibility, deployment, rollback, known issues, deviations, approval, corrections and addenda.

## 14.1 Release records

Every release that reaches users or production has a record at `docs/releases/<version>.md` (for example `docs/releases/1.4.0.md`) using [`release-template.md`](../project-template/docs/templates/release-template.md), indexed in `docs/releases/README.md`.

## 14.2 Statuses

`Planned` -> `Candidate` -> `Released`; `Released` -> `Withdrawn` | `Superseded`. `Released` is set only after owner approval and successful deployment.

## 14.3 Required content

- **Source baseline:** release tag and commit (recorded after tagging, in the record or the index).
- **Specification baselines:** each included `SPEC-NNN` with the commit at which it was approved or last changed.
- **Verification references:** convergence outcome, verification summaries, external evidence.
- **Migrations:** data or schema changes, ordering, and verification.
- **Compatibility:** interface, data, and configuration compatibility.
- **Deployment:** procedure or runbook link.
- **Rollback:** procedure, data implications, and tested status.
- **Known issues and approved deviations:** with links to the affected artifacts.
- **Approval:** approver, approval mode, date.

## 14.4 Release approval

The owner approves after the release-readiness review (prompt [18](../prompts/18-release-readiness.md)). High-risk releases use `enhanced-owner-review`. Tags are annotated and immutable.

## 14.5 Corrections and addenda

Released records are not rewritten. Corrections are appended in an `Addenda` section with date and reason. A defective release is fixed by a new release that supersedes it or by withdrawing it, recorded in both records.
