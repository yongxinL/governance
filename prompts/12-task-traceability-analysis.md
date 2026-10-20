# Prompt 12: Task Traceability Analysis

**Mode:** Read-only (native analyze may produce its native report) · **Owning manual chapter:** [26](../manual/26-validation-and-quality-gates.md)

## Purpose
Confirm native tasks cover every material requirement, acceptance criteria have verification coverage, no excluded scope is implemented, dependencies are ordered, documentation and operations tasks exist, and owner gates are visible.

## Mode
Read-only (native analyze may produce its native report).

## Required inputs
- Approved specification and plan
- Native tasks

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapters 17, 26

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Native analyze is the primary mechanism; this prompt adds Nexora checks.

## Permitted actions
- Run native analyze.
- Produce a traceability summary.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Creating a separate task list.
- Editing tasks without owner instruction.

## Stop conditions
Stop and report to the Project Owner when:
- Uncovered material requirement or AC.

## Expected output
- Coverage table (FR/NFR/AC to tasks and verification)
- Excluded-scope check
- Dependency order issues
- Missing documentation or operations tasks
- Owner gate list

## Owner decisions required
- Acceptance of gaps or task changes

## Validation criteria
- Every material requirement has implementation coverage
- Every AC has verification coverage

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Task Traceability Analysis.
Purpose: Confirm native tasks cover every material requirement, acceptance criteria have verification coverage, no excluded scope is implemented, dependencies are ordered, documentation and operations tasks exist, and owner gates are visible.
Mode: Read-only (native analyze may produce its native report).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 17, 26.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/12-task-traceability-analysis.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Coverage table (FR/NFR/AC to tasks and verification); Excluded-scope check; Dependency order issues; Missing documentation or operations tasks; Owner gate list.
End with the list of decisions required from the Project Owner.
```
