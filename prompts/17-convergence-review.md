# Prompt 17: Convergence Review

**Mode:** Read-only (native converge may write its native output)  
**Owning manual chapter:** [07](../manual/07-spec-kit-standard.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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

### Convergence classification

The native converge operation may create only its native output. Classify each artifact area as `CONVERGED`, `MINOR_DIVERGENCE`, `MATERIAL_DIVERGENCE`, `NOT_ASSESSED`, or `NOT_APPLICABLE`. Material divergence blocks status transition. Never alter an approved specification merely to match implementation.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Convergence Review.
Purpose: Use native Spec Kit convergence to compare specification, plan, tasks, code, tests, evidence, documentation, operations, and release preparation.
Mode: Read-only (native converge may write its native output).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, All native artifacts for the feature, Central manual chapters 07, 26.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/17-convergence-review.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Divergence table by artifact; Recommended resolution per item.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
