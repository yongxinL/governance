# Prompt 21: Agent Switch Handoff

**Mode:** Write (handoff file only) · **Owning manual chapter:** [19](../manual/19-agent-switching-and-handoffs.md)

## Purpose
Prepare a repository-based handoff when switching agents or pausing incomplete work.

## Mode
Write (handoff file only).

## Required inputs
- Current branch

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 19
- Handoff template

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The handoff is temporary and never replaces authoritative artifacts.

## Permitted actions
- Record branch, commit, specification, task state, completed and remaining work, tests, failures, uncommitted files, deviations, decisions needed, next action.
- Review integration-generated changes if the integration changes.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Copying conversation transcripts.
- Recreating or relocating authoritative artifacts.

## Stop conditions
Stop and report to the Project Owner when:
- Uncommitted changes that cannot be explained.

## Expected output
- `HANDOFF.md` on the branch
- Summary of integration changes reviewed

## Owner decisions required
- Decisions listed in the handoff
- Primary-agent change in the adoption record

## Validation criteria
- All mandatory handoff sections completed

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Agent Switch Handoff.
Purpose: Prepare a repository-based handoff when switching agents or pausing incomplete work.
Mode: Write (handoff file only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 19, Handoff template.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/21-agent-switch-handoff.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: `HANDOFF.md` on the branch; Summary of integration changes reviewed.
End with the list of decisions required from the Project Owner.
```
