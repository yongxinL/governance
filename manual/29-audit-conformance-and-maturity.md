# 29. Audit, Conformance, and Maturity

**Part VI** · Owns: adoption statuses, mandatory conformance controls, domain assessments, critical findings, maturity levels, trigger-based audits, read-only audit, incremental adoption, retirement review.

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

## 29.4 Critical findings

A breach of NX-1 to NX-6 is critical and is reported first, with immediate containment actions recommended.

## 29.5 Maturity levels (optional)

| Level | Name | Meaning |
|---|---|---|
| 1 | Controlled | Mandatory controls met; new work follows the gates. Normal target for a new solo project. |
| 2 | Traceable | Requirements trace to evidence and releases consistently. |
| 3 | Resilient | Operations, backup, and recovery exercised; lessons incorporated. |
| 4 | Assured | Independent review and external obligations met where applicable. |

## 29.6 Trigger-based audits

Initial adoption · migration completion · major governance upgrade · significant incident · major risk change · ownership or contributor-access change · external exposure change · project retirement · uncertain documentation integrity.

## 29.7 Read-only audits

Audits do not move, merge, rewrite, archive, or delete content; install tools; change configuration; or commit. They produce findings and recommendations (prompt [22](../prompts/22-governance-conformance-audit.md)).

## 29.8 Incremental adoption

Existing projects do not need retrospective specifications for historical features; see [chapter 06](06-specification-driven-development.md#67-existing-projects).

## 29.9 Retirement review

On retirement: final release record, operations shutdown runbook, credential revocation, archive of operational documentation where appropriate, adoption state `Retired`.
