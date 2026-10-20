# Verification Summary: <Scope> (YYYY-MM-DD)

> **Template (non-authoritative).** Place with the native feature artifacts where supported, or in `docs/testing/verification-<kebab-title>-YYYY-MM-DD.md`. A summary records evidence; it is not approval.

| Field | Value |
|---|---|
| Scope | *SPEC-NNN or project-wide* |
| Verified commit | *Commit SHA under test* |
| Environment | |
| Date | YYYY-MM-DD |
| Performed by | *Person or agent (agent results require owner review)* |
| Result | *Canonical outcome, one of `PASS` / `FAIL` / `BLOCKED` / `NOT_RUN` / `NOT_APPLICABLE`* |

## 0. Canonical outcomes and mapping (Mandatory)

Record every individual check with exactly one canonical outcome:

| Outcome | Meaning |
|---|---|
| `PASS` | The check ran and satisfied its requirement |
| `FAIL` | The check ran and did not satisfy its requirement |
| `BLOCKED` | The check could not run; a prerequisite or safety condition was unresolved |
| `NOT_RUN` | The check was not executed. No result is claimed. |
| `NOT_APPLICABLE` | The check does not apply, with a recorded reason |

A check that was not run is `NOT_RUN`. It is never `PASS` and never `FAIL`, and an
unavailable prerequisite is `BLOCKED`, never silently satisfied.

Human-facing summary wording may be used, and maps onto canonical outcomes only
as follows:

| Summary wording | Canonical outcomes that may compose it |
|---|---|
| Passed | All required checks `PASS`; none `NOT_RUN`, `FAIL`, or `BLOCKED` |
| Passed with approved deviations | All required checks `PASS` except deviations the Project Owner has actually accepted, each recorded with approver, mode, and date |
| Failed | At least one required check `FAIL` |
| Incomplete | At least one required check `NOT_RUN`, or `NOT_APPLICABLE` without a recorded reason |
| Blocked | At least one required check `BLOCKED` |

"Passed with approved deviations" asserts an approval that occurred. Without
recorded Project Owner approval, report `Failed` or `Incomplete` instead.

## 1. Acceptance-criteria results (Mandatory)

Classify every acceptance criterion and every applicable non-functional
requirement. Use canonical outcomes in the Result column.

| AC or NFR | Command or mechanism | Outcome | Evidence path | Limitation |
|---|---|---|---|---|

## 2. Commands run (Mandatory)
*Exact commands and outcomes. Never list a check that was not run.*

## 3. Failures and deviations (Mandatory; "none" if none)
## 4. External evidence references (Optional)
## 5. Not applicable items (Mandatory where any)
*Each with a reason.*
## 6. Unresolved issues (Mandatory; "none" if none)
*Anything still open, and who owns the next decision.*

## 7. Owner review (Mandatory)
*Reviewed by, approval mode, date. Leave unresolved until a real decision occurs;
this template does not pre-populate approval evidence.*

A summary records evidence; it never grants approval. Report what was verified at
this commit: evidence from a different commit does not verify this one.
