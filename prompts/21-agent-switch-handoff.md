# Prompt 21: Agent Switch Handoff

**Mode:** Write (handoff file only)  
**Owning manual chapter:** [19](../manual/19-agent-switching-and-handoffs.md)

## Purpose
Prepare a repository-based handoff when switching agents or pausing incomplete work.

## Mode
Write (handoff file only).

## Required inputs
- Current branch

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 19
- Handoff template

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The handoff is temporary and never replaces authoritative artifacts.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Record branch, commit, specification, task state, completed and remaining work, tests, failures, uncommitted files, deviations, decisions needed, next action.
- Review integration-generated changes if the integration changes.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Copying conversation transcripts.
- Recreating or relocating authoritative artifacts.

## Stop conditions
Stop and report to the Project Owner when:
- Uncommitted changes that cannot be explained.

## Expected output
- `HANDOFF.md` on the branch
- Summary of integration changes reviewed

## Owner decisions required
- Decisions listed in the handoff
- Primary-agent change in the adoption record

### Write-scope and Git controls

This prompt writes one temporary handoff file and nothing else.

1. Record the working state: `git branch --show-current` and `git status --short`
   before writing, so the handoff captures the real uncommitted state.
2. Write only the handoff file. Do not modify any other path, and do not commit,
   stash, or discard the uncommitted work the handoff is meant to describe.
3. Run `git diff --check` and read the complete diff.
4. Confirm the handoff contains no transcripts, credentials, tokens, personal
   data, or secrets.
5. Report validation performed and validation not performed (`NOT_RUN` or
   `BLOCKED`, with the reason).
6. Review the working-tree state before reporting readiness.

Before any commit, and only when the Project Owner has authorized that commit:

1. Stage explicit paths. Never use `git add -A` without first reviewing the
   exact resulting staged list.
2. Run `git diff --cached --name-only` and confirm only intended paths are staged.
3. Run `git diff --cached --check`.
4. Read the complete staged diff.
5. Run the stage-specific validation for this prompt.
6. Scan staged content for sensitive data.
7. Report the working-tree state.

Prohibited: destructive cleanup; discarding or stashing work that is not yours to
discard; force operations; history rewriting; and any commit, push, merge, tag,
publication, deployment, branch deletion, or approval without explicit owner
authorization. Recovery must be non-destructive.

### Validation criteria
- All mandatory handoff sections completed

### Handoff lifecycle

Create root-level `HANDOFF.md` only for incomplete work or an actual handoff. Reference native task IDs rather than copying tasks. A bounded secondary-agent review does not change the primary-agent record. Update `governance-adoption.md` only when the declared primary agent or active Spec Kit integration changes. Delete `HANDOFF.md` before merge after its content is resolved into authoritative artifacts.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Agent Switch Handoff.
Purpose: Prepare a repository-based handoff when switching agents or pausing incomplete work.
Mode: Write (handoff file only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 19, Handoff template.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/21-agent-switch-handoff.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: `HANDOFF.md` on the branch; Summary of integration changes reviewed.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
