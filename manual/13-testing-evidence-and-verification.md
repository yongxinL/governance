# 13. Testing, Evidence, and Verification

**Part III** · Owns: evidence classes, acceptance-criteria mapping, functional and non-functional verification, automated and manual testing, summaries, external, temporary, and sensitive evidence, failed verification, sufficiency, risk proportionality.

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
