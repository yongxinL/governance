# Test Plan: <Scope title>

> **Template (non-authoritative).** Copy to `docs/testing/test-plan-<kebab-title>.md` for project-wide or cross-feature testing, or to the native feature directory where the installed workflow supports it. Tests do not redefine requirements.

| Field | Value |
|---|---|
| Title | |
| Status | Draft |
| Owner | project-owner |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |
| Covers | *SPEC-NNN, NFRs, or project-wide scope* |

## 1. Scope (Mandatory)
## 2. Risk assessment (Mandatory)
*What could go wrong and how severe; drives depth of testing.*

## 3. Coverage mapping (Mandatory)

| Requirement or AC | Verification method (automated, manual, external, not applicable) | Test location or procedure | Notes |
|---|---|---|---|

## 4. Environments and data (Mandatory)
*Environments, versions, and safe test data. No production data or credentials.*

## 5. Manual procedures (Optional)
*Numbered, reusable steps with expected results.*

## 6. Non-functional verification (Mandatory where NFRs apply)
## 7. Entry and exit criteria (Mandatory)
## 8. Commands and mechanisms (Mandatory)

*Exact commands or procedures used to run each check, and where results are
recorded.*

| Check | Command or mechanism | Environment |
|---|---|---|

## 9. Result handling (Mandatory)

Record every check with one canonical outcome: `PASS`, `FAIL`, `BLOCKED`,
`NOT_RUN`, or `NOT_APPLICABLE`.

- A test that was not executed is `NOT_RUN`. It is never `PASS` and never `FAIL`.
- An unavailable prerequisite, environment, or dependency is `BLOCKED`; record the
  cause and what is needed to run it.
- `NOT_APPLICABLE` requires a stated reason.

Entry criteria are not met while any required check is `NOT_RUN` or `BLOCKED`.

## 10. Limitations and risks (Mandatory)
*What this plan does not cover, and the risk of the resulting blind spot.*

## 11. Completion and retention (Mandatory)
*When the plan is considered executed, who accepts the results, and how long
evidence is retained.*

## 12. Evidence to retain (Mandatory)
*Which summaries are committed and which evidence is referenced externally.*
