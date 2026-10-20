# Prompt 14: Implementation

**Mode:** Write (code, tests, documentation within authorized scope)  
**Owning manual chapter:** [18](../manual/18-ai-agent-standard.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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
- Every change traceable to a task
- Tests run and reported truthfully

### Implementation controls

Work only on authorized native tasks and keep each change traceable to task and requirement IDs. Review the working-tree diff before and after changes. If a required test cannot run, record it as `NOT_RUN`, explain the missing prerequisite or environment, preserve only safe bounded work, and stop at the validation boundary. Do not claim completion; the Project Owner decides any explicitly deferred validation.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Implementation.
Purpose: Implement authorized tasks in small, requirement-mapped changes with tests and documentation.
Mode: Write (code, tests, documentation within authorized scope).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Specification, plan, tasks, constitution, constraining ADRs.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/14-implementation.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Changed files with mapped requirement IDs; Commands run and results; Deviations; Remaining tasks.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
