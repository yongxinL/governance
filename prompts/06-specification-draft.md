# Prompt 06: Specification Draft

**Mode:** Write (native specification only)  
**Owning manual chapter:** [06](../manual/06-specification-driven-development.md)

## Purpose
Draft a native Spec Kit specification for a material change, allocate `SPEC-NNN`, and assign stable FR, NFR, and AC identifiers.

## Mode
Write (native specification only).

## Required inputs
- Feature description from the owner
- Product requirement served

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Native constitution
- Product requirements
- Constraining ADRs
- Specification index
- Central manual chapters 06, 07, 16

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Use the native specify command; the native template is the only specification format.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Run the native specify command for the active integration.
- Add the `SPEC-NNN` metadata block and identifiers inside the native specification.
- Add the index entry with status Draft.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Creating a separate Nexora specification file.
- Including implementation design or tasks.
- Marking the specification Approved.

## Stop conditions
Stop and report to the Project Owner when:
- The change is low-risk maintenance (no specification needed).
- Product intent is missing or contradictory.
- Material ambiguity requires owner decision.

## Expected output
- Native specification path
- Allocated SPEC ID
- Requirement and AC list with IDs
- Coverage notes for behaviour, interfaces, data, failure, security, compatibility, migration, verification, operations, rollback (or not applicable with reason)
- Open questions

## Owner decisions required
- Answers to open questions
- Move to In Review and approval

### Write-scope and Git controls

This prompt may change files. Before and during any change:

1. Record the working state: `git branch --show-current` and `git status --short`.
2. Confirm every path you intend to change is within the permitted scope for this
   prompt. Do not modify a path outside that scope.
3. Run `git diff --check` and resolve whitespace and conflict-marker defects.
4. Read the complete diff, not only the files you expected to change.
5. Confirm no authoritative content was overwritten silently, and no file was
   changed outside the permitted paths.
6. Report validation actually performed and validation not performed
   (`NOT_RUN` or `BLOCKED`, with the reason).
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
rewriting; and `git commit`, `git push`, `git merge`, `git tag`, publication,
deployment, branch deletion, or any approval without explicit owner
authorization.

Recovery guidance must be non-destructive. If work must be undone, restore or
revert the specific paths. Never assume discarded work is safe to lose.

### Validation criteria
- Every AC is testable
- IDs unique and sequential
- No duplicate specification location

### Native artifact controls

Use the installed Spec Kit integration's native `specify` entry point and native template. Allocate `SPEC-NNN` in the authoritative specification index, then add stable FR, NFR, and AC identifiers compatibly inside the native specification. Do not manually create `.specify/`, `specs/`, or a parallel Nexora specification.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Specification Draft.
Purpose: Draft a native Spec Kit specification for a material change, allocate `SPEC-NNN`, and assign stable FR, NFR, and AC identifiers.
Mode: Write (native specification only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Native constitution, Product requirements, Constraining ADRs, Specification index, Central manual chapters 06, 07, 16.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/06-specification-draft.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Native specification path; Allocated SPEC ID; Requirement and AC list with IDs; Coverage notes for behaviour, interfaces, data, failure, security, compatibility, migration, verification, operations, rollback (or not applicable with reason); Open questions.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
