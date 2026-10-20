# Prompt 02: Existing Project Read-Only Audit

**Mode:** Read-only · **Owning manual chapter:** [28](../manual/28-archive-retention-and-migration.md)

## Purpose
Inventory governed documentation and decision-bearing material in an existing repository and assess authority, status, duplication, conflicts, orphans, broken links, legacy content, and specification coverage.

## Mode
Read-only.

## Required inputs
- Repository at a recorded commit on an adoption branch

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapters 03, 17, 28, 29

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The audit describes; it does not decide authority.

## Permitted actions
- Read files; run read-only commands (listing, search, link checking).
- Write the audit report only to the conversation or to a path the owner names.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Moving, merging, rewriting, archiving, or deleting any file.
- Changing configuration or installing tools.
- Committing.
- Inventorying every source file individually.

## Stop conditions
Stop and report to the Project Owner when:
- Secrets or personal data are found (report location only, not the content).
- Repository state differs from the recorded commit.

## Expected output
- Inventory table: path, purpose, audience, type, status, authority, owner if known, current or historical, recommended action
- Lists: duplicates, conflicts, broken links, orphans, missing indexes, embedded requirements, embedded decisions
- Specification coverage by area
- Critical findings (non-exception control breaches) first

## Owner decisions required
- Authority for each conflicting category
- Treatment of sensitive findings

## Validation criteria
- Covers documentation, other formats, CI workflows, API schemas, environment examples, deployment definitions, decision-bearing source comments, tool and agent instructions
- No file modified (`git status` clean)

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Existing Project Read-Only Audit.
Purpose: Inventory governed documentation and decision-bearing material in an existing repository and assess authority, status, duplication, conflicts, orphans, broken links, legacy content, and specification coverage.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 03, 17, 28, 29.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/02-existing-project-read-only-audit.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Inventory table: path, purpose, audience, type, status, authority, owner if known, current or historical, recommended action; Lists: duplicates, conflicts, broken links, orphans, missing indexes, embedded requirements, embedded decisions; Specification coverage by area; Critical findings (non-exception control breaches) first.
End with the list of decisions required from the Project Owner.
```
