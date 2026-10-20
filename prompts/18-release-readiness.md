# Prompt 18: Release Readiness

**Mode:** Read-only  
**Owning manual chapter:** [14](../manual/14-release-management.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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

### Readiness classification

Verify exact source tag and commit, every included specification baseline, convergence outcomes, verification references, migrations, compatibility, deployment, rollback and tested status, known issues, deviations, and approval readiness.

Map the recommendation to the canonical gate outcomes `PASS`, `FAIL`, `BLOCKED`,
`NOT_RUN`, and `NOT_APPLICABLE`:

- `READY` requires every mandatory release gate to be `PASS`, the release record
  complete, generated artifacts and `MANIFEST.json` regenerated from final source,
  and a clean archive extraction validated. `READY` is permitted only if every
  mandatory gate passed, or where the manual explicitly permits an
  owner-approved deviation **and that approval already exists in the repository**.
  A deviation that is merely proposed is not an approval and yields
  `CONDITIONALLY_READY` at best.
- `CONDITIONALLY_READY` means the release could proceed once named, recorded
  conditions are met. Every condition is stated with its owner and evidence
  requirement.
- `NOT_READY` applies when any mandatory gate is `FAIL` or `BLOCKED`, or when
  release bytes are not final.

An unperformed gate is `NOT_RUN` and never counts toward `READY`.

This prompt only recommends. It does not set `Released`, assign a release date,
create a tag, publish, deploy, or rewrite a released record. Release approval is
a separate Project Owner decision.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Release Readiness.
Purpose: Review source baseline, specification baselines, verification, migration, compatibility, security, deployment, rollback, operations, known issues, deviations, and approval readiness.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 14, Included specifications and convergence outcomes, Runbooks.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/18-release-readiness.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Section checklist; Blocking items; Recommendation.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
