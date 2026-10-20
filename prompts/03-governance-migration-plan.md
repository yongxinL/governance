# Prompt 03: Governance Migration Plan

**Mode:** Read-only (plan output only)  
**Owning manual chapter:** [28](../manual/28-archive-retention-and-migration.md)

## Purpose
Convert audit findings into a migration map of safe automatic changes, careful consolidation, and Project Owner decisions, sequenced into controlled batches.

## Mode
Read-only (plan output only).

## Required inputs
- Completed read-only audit report

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapters 17, 28

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Authority must be resolved before any move; the plan proposes, the owner approves.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Classify every finding.
- Propose batches in the order: governance and indexes, safe moves and link repair, ADR and RFC normalization, specification registration, duplicate consolidation, metadata and traceability, validation, legacy archive.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Performing any migration.
- Classifying deletion or archive of possibly current content as safe automatic.
- Proposing retrospective specifications for the whole system.

## Stop conditions
Stop and report to the Project Owner when:
- Unresolved authority conflict blocks later batches.

## Expected output
- Migration map table: item, finding, class, proposed action, batch, dependencies
- Owner decision list
- Proposed source-of-truth register updates
- Proposed exceptions, if any

## Owner decisions required
- Every item in the owner-decision class
- Approval of the map

## Validation criteria
- Every audit finding mapped exactly once
- Authority resolution precedes moves
- No action executed

### Migration classes

Classify each finding exactly once as:

- `SAFE_AUTOMATIC`: batch-approved only after authority is resolved;
- `CAREFUL_CONSOLIDATION`: per-item review;
- `OWNER_DECISION`: explicit owner decision required.

Deletion or archiving of possibly current content is never `SAFE_AUTOMATIC`. Preserve canonical completed artifacts in their owning locations rather than archiving them merely because they are complete.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Governance Migration Plan.
Purpose: Convert audit findings into a migration map of safe automatic changes, careful consolidation, and Project Owner decisions, sequenced into controlled batches.
Mode: Read-only (plan output only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 17, 28.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/03-governance-migration-plan.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Migration map table: item, finding, class, proposed action, batch, dependencies; Owner decision list; Proposed source-of-truth register updates; Proposed exceptions, if any.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
