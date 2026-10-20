# 29. Audit, Conformance, and Maturity

**Part VI** · **Owns:** adoption statuses, mandatory conformance controls, domain assessments, critical findings, maturity levels, trigger-based audits, read-only audit, incremental adoption, retirement review.

## 29.1 Adoption states

`Not Adopted` · `Adoption in Progress` · `Adopted with Exceptions` · `Adopted` · `Retired`. Recorded in `governance-adoption.md`.

## 29.2 Mandatory conformance controls (Level 1 baseline)

1. Adoption record complete with version, tag, owner, mode, primary agent, integration.
2. Source-of-truth register present and accurate.
3. Area indexes present.
4. `AGENTS.md` present and consistent with governance.
5. Native constitution approved and reconciled.
6. No competing specification, plan, task, or completion authority.
7. Credentials absent from the repository.
8. Conditional tools disabled unless registered.
9. Exceptions recorded with required fields.

## 29.3 Domain assessments

Assess each domain (governance, product, specifications, decisions, testing and evidence, releases, operations, tooling and security, agents, indexing) as: `Not Applicable` · `Not Assessed` · `Needs Attention` · `Partially Conformant` · `Conformant`. No percentage score is used.

## 29.4 Findings and severity

Every audit finding records one severity:

| Severity | Meaning | Effect |
|---|---|---|
| `BLOCKING` | Breaches a foundational control, a mandatory gate, or package integrity | Stops the release or adoption until resolved |
| `MAJOR` | Material governance defect that is not foundational | Resolve before release, or reclassify with recorded rationale and owner acceptance |
| `MINOR` | Localized weakness with no material governance impact | Track and resolve proportionately |

A breach of NX-1 to NX-6 (chapter 01) is always `BLOCKING`, is reported first,
and carries recommended immediate containment.

Each check behind a finding uses the canonical outcomes `PASS`, `FAIL`,
`BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE`
([chapter 13](13-testing-evidence-and-verification.md#1311-canonical-check-outcomes-and-their-mapping)).
A domain that was not examined is `NOT_RUN` and is never reported as conformant.
Domain ratings in 29.3 are descriptive; they never substitute for a severity,
and they never override a `BLOCKING` finding.

Audit evidence is scoped to a named repository version and commit. An audit of one
commit does not verify a later one, and an unperformed check is `NOT_RUN`, never
an implied pass.

An auditor, including an AI agent, reports findings and recommendations. It never
approves its own material governance change, and an audit never substitutes for
Project Owner approval ([chapter 05](05-lifecycle-ownership-and-approvals.md)).

## 29.5 Maturity levels (optional)

| Level | Name | Meaning |
|---|---|---|
| 1 | Controlled | Mandatory controls met; new work follows the gates. Normal target for a new solo project. |
| 2 | Traceable | Requirements trace to evidence and releases consistently. |
| 3 | Resilient | Operations, backup, and recovery exercised; lessons incorporated. |
| 4 | Assured | Independent review and external obligations met where applicable. |

Maturity is optional and additive. A higher maturity level never compensates for a
missing mandatory control or a failed release gate. Level 4 with a `BLOCKING`
finding is still not conforming, and maturity is never awarded for an unperformed
exercise.

## 29.6 Trigger-based audits

Initial adoption · migration completion · major governance upgrade · significant incident · major risk change · ownership or contributor-access change · external exposure change · project retirement · uncertain documentation integrity.

## 29.7 Read-only audits

Audits do not move, merge, rewrite, archive, or delete content; install tools; change configuration; or commit. They produce findings and recommendations (prompt [22](../prompts/22-governance-conformance-audit.md)).

## 29.8 Incremental adoption

Existing projects do not need retrospective specifications for historical features; see [chapter 06](06-specification-driven-development.md#67-existing-projects).

## 29.9 Retirement review

On retirement: final release record, operations shutdown runbook, credential revocation, archive of operational documentation where appropriate, adoption state `Retired`.
