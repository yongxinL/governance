# Prompt 15: Ponytail Quality Review

**Mode:** Read-only (review-only pilot) · **Owning manual chapter:** [24](../manual/24-ponytail-standard.md)

## Purpose
Perform review-only analysis of a completed change for unnecessary code and dependencies, reuse opportunities, bugs, security issues, missing tests, performance, risky complexity, and maintainability.

## Mode
Read-only (review-only pilot).

## Required inputs
- Completed change (diff or branch)
- Ponytail registered in Pilot state

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Specification and constitution
- Central manual chapter 24

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Ponytail findings are suggestions; approved requirements and controls prevail.

## Permitted actions
- Review the diff and produce findings.
- Record pilot metrics.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Editing code.
- Proposing removal of requirements, tests, security, accessibility, observability, error handling, recovery, rollback, or documentation.
- Enabling Ponytail hooks.

## Stop conditions
Stop and report to the Project Owner when:
- Ponytail not registered.

## Expected output
- Findings table: location, category, suggestion, risk
- Rejected-by-rule list (suggestions that would weaken controls)
- Pilot metrics entry

## Owner decisions required
- Disposition of each finding

## Validation criteria
- No weakening suggestion presented as acceptable

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Ponytail Quality Review.
Purpose: Perform review-only analysis of a completed change for unnecessary code and dependencies, reuse opportunities, bugs, security issues, missing tests, performance, risky complexity, and maintainability.
Mode: Read-only (review-only pilot).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Specification and constitution, Central manual chapter 24.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/15-ponytail-quality-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Findings table: location, category, suggestion, risk; Rejected-by-rule list (suggestions that would weaken controls); Pilot metrics entry.
End with the list of decisions required from the Project Owner.
```
