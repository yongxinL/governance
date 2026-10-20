# Prompt 18: Release Readiness

**Mode:** Read-only · **Owning manual chapter:** [14](../manual/14-release-management.md)

## Purpose
Review source baseline, specification baselines, verification, migration, compatibility, security, deployment, rollback, operations, known issues, deviations, and approval readiness.

## Mode
Read-only.

## Required inputs
- Draft release record (Candidate)

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 14
- Included specifications and convergence outcomes
- Runbooks

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Release approval is the owner's.

## Permitted actions
- Check each release record section against evidence.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Tagging, publishing, or deploying.

## Stop conditions
Stop and report to the Project Owner when:
- Missing rollback for a release with migrations.
- Unconverged included specification.

## Expected output
- Section checklist
- Blocking items
- Recommendation

## Owner decisions required
- Release approval

## Validation criteria
- All mandatory sections evidenced

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Release Readiness.
Purpose: Review source baseline, specification baselines, verification, migration, compatibility, security, deployment, rollback, operations, known issues, deviations, and approval readiness.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 14, Included specifications and convergence outcomes, Runbooks.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/18-release-readiness.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Section checklist; Blocking items; Recommendation.
End with the list of decisions required from the Project Owner.
```
