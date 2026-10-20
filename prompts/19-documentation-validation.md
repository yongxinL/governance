# Prompt 19: Documentation Validation

**Mode:** Read-only · **Owning manual chapter:** [26](../manual/26-validation-and-quality-gates.md)

## Purpose
Check indexes, metadata, identifiers, links, statuses, orphans, stale paths, source-of-truth integrity, archive rules, unexplained authoring markers, and generated-file authority.

## Mode
Read-only.

## Required inputs
- Repository

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapters 16, 17, 26, 27, 28

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Findings only; fixes follow owner approval.

## Permitted actions
- Run link and structure checks.
- Search for unexplained authoring markers (TODO, TBD, Coming soon, Write this section, Add details, Lorem ipsum) and unresolved customization markers.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Editing files.

## Stop conditions
Stop and report to the Project Owner when:
- None; report all findings.

## Expected output
- Findings table with severity (blocking, major, minor)
- Orphan classification
- Index-versus-artifact mismatches

## Owner decisions required
- Disposition of major findings

## Validation criteria
- All checks in the purpose statement executed

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Documentation Validation.
Purpose: Check indexes, metadata, identifiers, links, statuses, orphans, stale paths, source-of-truth integrity, archive rules, unexplained authoring markers, and generated-file authority.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 16, 17, 26, 27, 28.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/19-documentation-validation.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Findings table with severity (blocking, major, minor); Orphan classification; Index-versus-artifact mismatches.
End with the list of decisions required from the Project Owner.
```
