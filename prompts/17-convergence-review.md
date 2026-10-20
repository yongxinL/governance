# Prompt 17: Convergence Review

**Mode:** Read-only (native converge may write its native output) · **Owning manual chapter:** [07](../manual/07-spec-kit-standard.md)

## Purpose
Use native Spec Kit convergence to compare specification, plan, tasks, code, tests, evidence, documentation, operations, and release preparation.

## Mode
Read-only (native converge may write its native output).

## Required inputs
- Implemented feature

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- All native artifacts for the feature
- Central manual chapters 07, 26

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Completion requires convergence plus owner acceptance.

## Permitted actions
- Run native converge.
- Summarize divergence.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Marking complete with material divergence.
- Changing specifications to match code silently.

## Stop conditions
Stop and report to the Project Owner when:
- Material divergence found.

## Expected output
- Divergence table by artifact
- Recommended resolution per item

## Owner decisions required
- Acceptance of convergence and status transition

## Validation criteria
- Every artifact class compared

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Convergence Review.
Purpose: Use native Spec Kit convergence to compare specification, plan, tasks, code, tests, evidence, documentation, operations, and release preparation.
Mode: Read-only (native converge may write its native output).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, All native artifacts for the feature, Central manual chapters 07, 26.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/17-convergence-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Divergence table by artifact; Recommended resolution per item.
End with the list of decisions required from the Project Owner.
```
