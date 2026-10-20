# 14. Release Management

**Part III** · **Owns:** release records, release status, source baseline, specification baselines, verification references, migrations, compatibility, deployment, rollback, known issues, deviations, approval, corrections and addenda.

## 14.1 Release records

Every release that reaches users or production has a record at `docs/releases/<version>.md` (for example `docs/releases/1.4.0.md`) using [`release-template.md`](../project-template/docs/templates/release-template.md), indexed in `docs/releases/README.md`.

## 14.2 Statuses

`Planned` -> `Candidate` -> `Released`; `Released` -> `Withdrawn` | `Superseded`.

- **Planned:** the release is intended. Its tag does not exist yet.
- **Candidate:** package bytes, gates, and the release record are complete and
  awaiting the owner's release decision.
- **Released:** set only after owner approval and successful deployment.
- **Withdrawn:** the release is no longer supported or was found defective.
- **Superseded:** a later release replaces it.

Readiness and approval are distinct. A release-readiness review (prompt
[18](../prompts/18-release-readiness.md)) produces a **recommendation**. Only the
Project Owner sets `Released`. A passing readiness review is never itself the
release approval.

Release status and release date must never be pre-populated. While a release is
in preparation, its record states the planned tag and `Pending` for the date. A
tag that does not exist must not be described as existing.

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

## 14.5 Publication evidence

Order is fixed and each step depends on the previous one:

1. All source content is final.
2. Generated artifacts, including `instructions/README.html`, are regenerated
   from that final source.
3. Release gates pass.
4. `MANIFEST.json` is regenerated last, from the final bytes.
5. The deterministic release archive is built and validated by clean extraction
   into an empty directory.
6. The archive byte size and SHA-256 are reported externally.
7. The owner gives explicit final-release authorization.
8. Only then is the immutable tag created and the release published.

A release claim requires publication evidence. Do not state that a release is
published, tagged, or available before the tag exists and the publication
record does. Generated artifacts and the manifest must describe the same bytes
that are actually distributed.

### 14.5.1 Missing historical tags

A release record remains truthful when an expected tag cannot be found. Record
what is verifiable: the declared status, the declaration date, and the source
baseline commit. State plainly that no tag was found rather than asserting that
one exists or that the release never happened. This package does not create
retrospective tags; that is a separate owner decision.

## 14.6 Corrections and addenda

Released records are not rewritten. Corrections are appended in an `Addenda` section with date and reason. A defective release is fixed by a new release that supersedes it or by withdrawing it, recorded in both records.
