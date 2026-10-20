# 13. Testing, Evidence, and Verification

**Part III** · **Owns:** evidence classes, acceptance-criteria mapping, functional and non-functional verification, automated and manual testing, summaries, external, temporary, and sensitive evidence, failed verification, sufficiency, risk proportionality.

## 13.1 Evidence classes

| Class | Examples | Commit? |
|---|---|---|
| Repository evidence | Automated tests, repeatable verification scripts, safe fixtures | Yes |
| Committed evidence summaries | Verification summaries, migration evidence, backup-restore exercise summaries, `bug` extension records, release records, known deviations | Yes |
| Referenced external evidence | CI run URLs, scanner dashboards, large reports stored elsewhere | Reference only |
| Temporary working evidence | Debug traces, screenshots, raw logs, AI transcripts | No |

Never commit by default: routine CI logs, raw build logs, coverage websites, large scanner exports, temporary screenshots, debug traces, AI conversation transcripts, dependency caches, reproducible build output, or sensitive information.

## 13.2 Locations

- Feature evidence: with native Spec Kit artifacts where the installed workflow provides a location (for example a verification summary in the feature directory).
- Defect evidence under the `bug` extension: `.specify/bugs/<slug>/test.md` (limit B6).
- Project-wide: `docs/testing/` for test strategy, cross-feature verification, compatibility matrices, project-wide security and performance evidence, reusable manual procedures.
- Release-level: the release record.

## 13.3 Acceptance-criteria mapping

Each `SPEC-NNN-AC-NNN` and applicable `SPEC-NNN-NFR-NNN` maps to one or more of: automated test, manual procedure with recorded result, external evidence reference, or `not applicable` with reason. Unmapped criteria block convergence.

## 13.4 Functional and non-functional verification

Non-functional requirements (performance, security, accessibility, reliability, observability, recoverability) require evidence proportional to risk: a measured result, a scan, an exercise, or a reasoned review for low risk.

## 13.5 Automated and manual testing

Prefer automated tests for repeatable behaviour. Manual verification uses a reusable procedure (test-plan template) and records the date, environment, version, and result in a verification summary.

## 13.6 Sensitive evidence

Redact or reference. Never commit credentials, tokens, personal data, production data extracts, cookies, or authenticated browser state. Screenshots and traces from Playwright are presumed sensitive ([chapter 25](25-playwright-and-remote-integrations.md)).

## 13.7 Failed verification

Record the failure, do not mark tasks complete, decide (owner) whether to fix, change the specification through control, or accept a known deviation recorded in the release record. Recurring failures produce a lesson.

## 13.8 Sufficiency and proportionality

Evidence is sufficient when an informed reviewer could reasonably conclude every material acceptance criterion is met. High-risk work requires failure-path evidence and rollback evidence. Low-risk maintenance relies on the existing test suite passing.

## 13.9 Templates and prompts

[`test-plan-template.md`](../project-template/docs/templates/test-plan-template.md), [`verification-summary-template.md`](../project-template/docs/templates/verification-summary-template.md), prompt [16](../prompts/16-test-and-evidence-review.md).

### 13.10 Verification result vocabulary

Use these summary results:

- `Passed`: all required verification passed.
- `Passed with approved deviations`: required verification passed except for
  deviations explicitly accepted by the Project Owner.
- `Failed`: a check ran and did not satisfy its requirement.
- `Incomplete`: required evidence is missing or a required check was not run.
- `Blocked`: verification cannot proceed because a prerequisite or safety
  condition is unresolved.

A check that was not run is recorded as `NOT_RUN`, never as passed or failed.

### 13.11 Canonical check outcomes and their mapping

Every individual check records exactly one canonical outcome. These are the
values used by the prompts, release gates, and validation output:

| Outcome | Meaning |
|---|---|
| `PASS` | The check ran and satisfied its requirement. |
| `FAIL` | The check ran and did not satisfy its requirement. |
| `BLOCKED` | The check could not run because a prerequisite or safety condition was unresolved. |
| `NOT_RUN` | The check was not executed. No result is claimed. |
| `NOT_APPLICABLE` | The check does not apply to this change, with a recorded reason. |

The summary results in 13.10 are human-facing and map onto canonical outcomes as
follows. They are not a second, competing vocabulary.

| Summary result | Canonical outcomes that may compose it |
|---|---|
| `Passed` | All required checks `PASS`; no required check `NOT_RUN`, `FAIL`, or `BLOCKED` |
| `Passed with approved deviations` | All required checks `PASS` except deviations the Project Owner has explicitly accepted, each recorded with approver, mode, and date |
| `Failed` | At least one required check `FAIL` |
| `Incomplete` | At least one required check `NOT_RUN` or `NOT_APPLICABLE` without a recorded reason |
| `Blocked` | At least one required check `BLOCKED` |

Rules:

- A check outcome is never inferred from a summary result, and a summary result
  is never inferred from a single check outcome.
- "Passed with approved deviations" is a claim about an approval that actually
  occurred. Without a recorded Project Owner approval it must be reported as
  `Failed` or `Incomplete`, never as passed with deviations.
- Reporting completion must distinguish validation performed from validation not
  performed. If any required check was not run, the work is not fully verified,
  whatever else succeeded.
- Evidence is scoped to a specific version and commit. Evidence from a
  different revision does not verify the current one.
- `BLOCKED` is never reported as `PASS`, and an unavailable prerequisite is
  never silently treated as satisfied.
