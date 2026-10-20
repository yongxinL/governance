# Prompt 16: Test and Evidence Review

**Mode:** Read-only · **Owning manual chapter:** [13](../manual/13-testing-evidence-and-verification.md)

## Purpose
Map tests and evidence to acceptance criteria and applicable NFRs and identify unsupported completion claims.

## Mode
Read-only.

## Required inputs
- Specification
- Tests
- Verification summaries
- `bug` extension `test.md` where applicable

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 13

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Evidence is not approval; `verified` in a bug record is not approval.

## Permitted actions
- Classify evidence as automated, manual, external, temporary, missing, or not applicable.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Marking tasks complete.
- Committing raw sensitive evidence.

## Stop conditions
Stop and report to the Project Owner when:
- Evidence contains secrets or personal data.

## Expected output
- AC/NFR-to-evidence table
- Missing evidence
- Unsupported completion claims

## Owner decisions required
- Acceptance of gaps or known deviations

## Validation criteria
- Every AC classified

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Test and Evidence Review.
Purpose: Map tests and evidence to acceptance criteria and applicable NFRs and identify unsupported completion claims.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 13.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/16-test-and-evidence-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: AC/NFR-to-evidence table; Missing evidence; Unsupported completion claims.
End with the list of decisions required from the Project Owner.
```
