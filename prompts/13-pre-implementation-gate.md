# Prompt 13: Pre-Implementation Gate

**Mode:** Read-only  
**Owning manual chapter:** [26](../manual/26-validation-and-quality-gates.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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

### Gate decision

Pass only when all chapter 26 pre-implementation conditions are evidenced. Check the project test, build, and lint commands in `AGENTS.md`; unresolved command markers block readiness unless explicitly documented as not applicable. Recommend `PASS` or `BLOCKED`; only the Project Owner authorizes implementation.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Pre-Implementation Gate.
Purpose: Confirm everything required to start implementation is in place.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, All applicable authority listed in `AGENTS.md`, Central manual chapter 26.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/13-pre-implementation-gate.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Gate checklist with pass or fail and evidence paths; Blocking items.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
