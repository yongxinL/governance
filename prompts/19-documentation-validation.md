# Prompt 19: Documentation Validation

**Mode:** Read-only  
**Owning manual chapter:** [26](../manual/26-validation-and-quality-gates.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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

### Generated and source content

Distinguish, as separate finding classes:

- **Approved unresolved marker:** a documented customization marker that is
  correct and expected. Not a finding.
- **Intentionally pending field:** a field recorded as pending because the event
  has not occurred. Not a finding.
- **Stale placeholder:** a marker or example value left from an earlier release
  or another project. A finding.
- **Unexplained unresolved content:** placeholder-like text with no owning
  decision or explanation. A finding.
- **Generated/source divergence:** a generated file whose recorded source
  fingerprint does not match its source, or which was hand-edited.

A known intermediate divergence between a generated file and its authoritative
Markdown source is recorded as `NOT_RUN` or `BLOCKED` against final readiness, not
as a pass. It must be resolved before release readiness, and its presence is
never reported as documentation validation success.

## Expected output
- Findings table with severity (`BLOCKING`, `MAJOR`, `MINOR`)
- Orphan classification
- Index-versus-artifact mismatches

## Owner decisions required
- Disposition of major findings

## Validation criteria
- All checks in the purpose statement executed

### Documentation checks

Run structural, content, link, and semantic checks from chapter 26. For customization markers, classify each as `RESOLVED`, `APPROVED_UNRESOLVED`, `UNEXPLAINED_UNRESOLVED`, `STALE`, or `NOT_APPLICABLE`. Indexes are authoritative for identity, location, status, supersession, and baseline; linked artifacts own their full content.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Documentation Validation.
Purpose: Check indexes, metadata, identifiers, links, statuses, orphans, stale paths, source-of-truth integrity, archive rules, unexplained authoring markers, and generated-file authority.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 16, 17, 26, 27, 28.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/19-documentation-validation.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Findings table with severity (blocking, major, minor); Orphan classification; Index-versus-artifact mismatches.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
