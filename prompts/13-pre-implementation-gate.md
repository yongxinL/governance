# Prompt 13: Pre-Implementation Gate

**Mode:** Read-only · **Owning manual chapter:** [26](../manual/26-validation-and-quality-gates.md)

## Purpose
Confirm everything required to start implementation is in place.

## Mode
Read-only.

## Required inputs
- Approved specification, plan, tasks
- Analysis result

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- All applicable authority listed in `AGENTS.md`
- Central manual chapter 26

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Implementation is authorized only by the owner.

## Permitted actions
- Check approvals, tool registrations, unresolved conflicts, security uncertainty, and rollback.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Starting implementation.

## Stop conditions
Stop and report to the Project Owner when:
- Any unresolved conflict, ambiguity, security uncertainty, missing approval, unregistered required tool, or missing rollback for risky change.

## Expected output
- Gate checklist with pass or fail and evidence paths
- Blocking items

## Owner decisions required
- Implementation authorization

## Validation criteria
- All checklist items evidenced

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Pre-Implementation Gate.
Purpose: Confirm everything required to start implementation is in place.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, All applicable authority listed in `AGENTS.md, Central manual chapter 26.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/13-pre-implementation-gate.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Gate checklist with pass or fail and evidence paths; Blocking items.
End with the list of decisions required from the Project Owner.
```
