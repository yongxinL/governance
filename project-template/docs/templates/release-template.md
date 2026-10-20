# Release <VERSION>

> **Template (non-authoritative).** Copy to `docs/releases/<version>.md`. Release records reference specification baselines; they never redefine specifications. Once Released, the record is corrected only through addenda.

| Field | Value |
|---|---|
| Version | |
| Status | Planned |
| Owner | project-owner |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |
| Release date | *Completed when Released* |
| Tag | *Annotated tag name* |
| Source commit | *Recorded after tagging* |
| Approved by / mode / date | *Completed on approval* |

## 1. Summary (Mandatory)

## 2. Included specifications (Mandatory)

| SPEC | Title | Baseline commit | Convergence outcome |
|---|---|---|---|

## 3. Other changes (Optional)
*Defect fixes (including `bug` extension slugs), maintenance.*

## 4. Verification references (Mandatory)
## 5. Migrations (Mandatory; "none" if none)
## 6. Compatibility (Mandatory)
## 7. Deployment (Mandatory)
*Runbook link.*
## 8. Rollback (Mandatory)
*Procedure, data implications, tested status.*
## 9. Known issues (Mandatory; "none" if none)
## 10. Approved deviations (Mandatory; "none" if none)
## 11. Release gates (Mandatory)

Record every mandatory release gate and its canonical outcome. All mandatory
gates must be `PASS` before release approval is requested.

| Gate | Outcome | Evidence |
|---|---|---|
| 1 Structure | `NOT_RUN` | |
| 2 Content completeness | `NOT_RUN` | |
| 3 Governance consistency | `NOT_RUN` | |
| 4 Authority and duplication | `NOT_RUN` | |
| 5 Security and tooling | `NOT_RUN` | |
| 6 Links, indexes, identifiers | `NOT_RUN` | |
| 7 Generated artifacts and manifest | `NOT_RUN` | |
| 8 Archive and release readiness | `NOT_RUN` | |

Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE`. A gate that was not
run is `NOT_RUN` and never counts as passed.

## 12. Generated artifacts and package identity (Mandatory)

*Record only what actually exists. Leave unresolved until the release bytes are
final.*

| Item | Value |
|---|---|
| Generated artifacts regenerated from final source | Pending |
| Manifest regenerated last | Pending |
| Release archive filename | Pending |
| Archive byte size | Pending |
| Archive SHA-256 | Pending |
| Clean extraction validated | Pending |

Do not record a checksum, archive, or manifest identity that was not produced.

## 13. Publication evidence (Mandatory)

*Complete only after publication actually occurs.*

| Item | Value |
|---|---|
| Immutable tag created | Pending |
| Tag points to recorded commit | Pending |
| Release published | Pending |
| Publication location | Pending |

Status may be set to `Released` only after owner approval and successful
publication. Do not claim a tag, date, or publication before it exists.

## 14. Addenda (Optional)
*Dated corrections after release.*
