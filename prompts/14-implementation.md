# Prompt 14: Implementation

**Mode:** Write (code, tests, documentation within authorized scope) · **Owning manual chapter:** [18](../manual/18-ai-agent-standard.md)

## Purpose
Implement authorized tasks in small, requirement-mapped changes with tests and documentation.

## Mode
Write (code, tests, documentation within authorized scope).

## Required inputs
- Implementation authorization
- Native tasks

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Specification, plan, tasks, constitution, constraining ADRs

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The approved specification governs; deviations are reported, not absorbed.

## Permitted actions
- Run the native implement command or work task by task.
- Write code and tests mapped to requirement IDs.
- Update documentation and native task state.
- Run test, build, and lint commands.
- For `bug` extension work: run `speckit.bug.fix` only after owner authorization of the assessment.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Silently changing approved specifications.
- Installing unapproved tools.
- Publishing, deploying, merging, tagging, or releasing without authorization.
- Expanding scope.

## Stop conditions
Stop and report to the Project Owner when:
- Specification defect discovered.
- Scope expansion needed.
- Tests cannot be run.
- Security or data risk.

## Expected output
- Changed files with mapped requirement IDs
- Commands run and results
- Deviations
- Remaining tasks

## Owner decisions required
- Deviation dispositions

## Validation criteria
- Every change traceable to a task
- Tests run and reported truthfully

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Implementation.
Purpose: Implement authorized tasks in small, requirement-mapped changes with tests and documentation.
Mode: Write (code, tests, documentation within authorized scope).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Specification, plan, tasks, constitution, constraining ADRs.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/14-implementation.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Changed files with mapped requirement IDs; Commands run and results; Deviations; Remaining tasks.
End with the list of decisions required from the Project Owner.
```
