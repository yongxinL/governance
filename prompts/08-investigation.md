# Prompt 08: Investigation

**Mode:** Write (investigation document and safe experiments)  
**Owning manual chapter:** [11](../manual/11-investigations-and-lessons.md)

## Purpose
Gather evidence to resolve a material uncertainty and record experiments, findings, limitations, options, and a recommendation.

## Mode
Write (investigation document and safe experiments).

## Required inputs
- Question to answer
- Blocked artifact

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 11
- Investigation template

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The investigation recommends; it does not decide.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Create `INV-NNN` from the template and index it.
- Run safe, non-destructive experiments in non-production environments.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Claiming decision authority.
- Using production systems or credentials without owner authorization.
- Committing raw sensitive evidence.

## Stop conditions
Stop and report to the Project Owner when:
- An experiment would be destructive or touch production.
- Evidence requires credentials not provided.

## Expected output
- Investigation document
- Evidence summary
- Recommendation and proposed decision artifact

## Owner decisions required
- Decision on the recommendation, recorded in the appropriate artifact

### Write-scope and Git controls

This prompt may change files. Before and during any change:

1. Record the working state: `git branch --show-current` and `git status --short`.
2. Confirm every path you intend to change is within the permitted scope for this
   prompt. Do not modify a path outside that scope.
3. Run `git diff --check` and resolve whitespace and conflict-marker defects.
4. Read the complete diff, not only the files you expected to change.
5. Confirm no authoritative content was overwritten silently.
6. Report validation actually performed and validation not performed
   (`NOT_RUN` or `BLOCKED`, with the reason and what is required to run it).
7. Review the working-tree state before reporting readiness.

Before any commit, and only when the Project Owner has authorized that commit:

1. Stage explicit paths or a reviewed patch. Never use `git add -A` without first
   reviewing the exact resulting staged list.
2. Run `git diff --cached --name-only` and confirm only intended paths are staged.
3. Run `git diff --cached --check`.
4. Read the complete staged diff.
5. Run the stage-specific validation for this prompt.
6. Scan staged content for credentials, tokens, private keys, cookies, and
   personal or production data.
7. Report the working-tree state.

Prohibited in every case: destructive cleanup for convenience; discarding
uncommitted work that is not yours to discard; force operations; history
rewriting; and any commit, push, merge, tag, publication, deployment, branch
deletion, or approval without explicit owner authorization.

Recovery guidance must be non-destructive. Restore or revert the specific paths
involved. Never assume discarded work is safe to lose.

### Validation criteria
- Limitations section present
- Evidence reproducible or referenced

### Investigation controls

Allocate `INV-NNN` in the investigation index. Record environment and versions for experiments, limitations, and evidence locations. A completed investigation ends the inquiry but does not approve its recommendation. Do not create the resulting ADR, RFC outcome, specification change, or exception unless separately authorized.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Investigation.
Purpose: Gather evidence to resolve a material uncertainty and record experiments, findings, limitations, options, and a recommendation.
Mode: Write (investigation document and safe experiments).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 11, Investigation template.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/08-investigation.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Investigation document; Evidence summary; Recommendation and proposed decision artifact.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
