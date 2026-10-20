# Prompt 22: Governance Conformance Audit

**Mode:** Read-only · **Owning manual chapter:** [29](../manual/29-audit-conformance-and-maturity.md)

## Purpose
Perform a read-only domain assessment to determine adoption state, control gaps, critical findings, exceptions, optional maturity, and recommended actions.

## Mode
Read-only.

## Required inputs
- Repository at a recorded commit
- Audit trigger

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 29
- `docs/governance/` records

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The audit recommends; it does not reorganize.

## Permitted actions
- Assess each domain.
- Assess mandatory controls.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Reorganizing, moving, merging, archiving, deleting, installing, configuring, or committing.

## Stop conditions
Stop and report to the Project Owner when:
- None; report all findings, critical first.

## Expected output
- Critical findings
- Domain assessment table
- Control gaps
- Exception review
- Optional maturity assessment
- Recommended actions

## Owner decisions required
- Response to critical findings
- Adoption state

## Validation criteria
- No percentage score used
- Every domain assessed or marked Not Assessed with reason

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Governance Conformance Audit.
Purpose: Perform a read-only domain assessment to determine adoption state, control gaps, critical findings, exceptions, optional maturity, and recommended actions.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 29, docs/governance/` records.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/22-governance-conformance-audit.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Critical findings; Domain assessment table; Control gaps; Exception review; Optional maturity assessment; Recommended actions.
End with the list of decisions required from the Project Owner.
```
