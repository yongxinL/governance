# Prompt 11: Plan Review

**Mode:** Read-only · **Owning manual chapter:** [12](../manual/12-planning-and-cross-specification-delivery.md)

## Purpose
Review the native Spec Kit plan against the approved specification and constitution.

## Mode
Read-only.

## Required inputs
- Approved specification
- Native plan

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Native constitution
- Constraining ADRs
- Central manual chapter 12

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The native plan is the only feature plan.

## Permitted actions
- Map plan components to requirement IDs.
- Identify speculative scope, constitution conflicts, and missing ADRs.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Writing an alternative plan.
- Adding requirements.

## Stop conditions
Stop and report to the Project Owner when:
- The specification is not Approved.
- The plan requires a new significant decision without an ADR.

## Expected output
- Requirement-to-plan mapping
- Findings with severity
- Recommendation

## Owner decisions required
- Plan approval

## Validation criteria
- Every material requirement mapped
- No competing plan created

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Plan Review.
Purpose: Review the native Spec Kit plan against the approved specification and constitution.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Native constitution, Constraining ADRs, Central manual chapter 12.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/11-plan-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Requirement-to-plan mapping; Findings with severity; Recommendation.
End with the list of decisions required from the Project Owner.
```
