# Prompt 09: RFC Review

**Mode:** Read-only · **Owning manual chapter:** [10](../manual/10-rfc-standard.md)

## Purpose
Review an RFC for completeness, alternatives, risk, security, data, operations, migration, testing, rollback, cost, reversibility, and success criteria.

## Mode
Read-only.

## Required inputs
- RFC in Draft or In Review

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 10
- Related investigations and ADRs

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The outcome is the owner's decision.

## Permitted actions
- Assess each mandatory section.
- Identify missing alternatives and risks.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Recording an outcome.
- Editing the RFC.

## Stop conditions
Stop and report to the Project Owner when:
- The RFC is really a single decision better recorded as an ADR (report it).

## Expected output
- Section-by-section assessment
- Risk summary
- Recommendation (accept, reject, defer, revise)

## Owner decisions required
- Outcome

## Validation criteria
- All 13 mandatory sections assessed

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: RFC Review.
Purpose: Review an RFC for completeness, alternatives, risk, security, data, operations, migration, testing, rollback, cost, reversibility, and success criteria.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 10, Related investigations and ADRs.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/09-rfc-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Section-by-section assessment; Risk summary; Recommendation (accept, reject, defer, revise).
End with the list of decisions required from the Project Owner.
```
