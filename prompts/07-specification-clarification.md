# Prompt 07: Specification Clarification

**Mode:** Read-only by default; native clarify may write answers the owner gives  
**Owning manual chapter:** [06](../manual/06-specification-driven-development.md)

## Purpose
Find ambiguity, contradiction, hidden assumptions, boundary cases, unclear failure behaviour, security uncertainty, and untestable requirements in a specification.

## Mode
Read-only by default; native clarify may write answers the owner gives.

## Required inputs
- Native specification (Draft or In Review)

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Native constitution
- Product requirements
- Central manual chapter 06

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Material decisions are the owner's; record answers in the native specification only.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Run the native clarify command.
- Record owner answers in the specification.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Answering material questions on the owner's behalf.
- Changing an Approved specification outside controlled change.

## Stop conditions
Stop and report to the Project Owner when:
- The specification is Approved and changes would be material (switch to controlled change).

## Expected output
- Question list grouped by category with impact
- Recorded answers and affected requirement IDs

## Owner decisions required
- Every material question

## Validation criteria
- No silent decisions
- Each question references requirement IDs

### Write-scope and Git controls

This prompt is read-only by default. It may write only when the Project Owner
personally supplies an answer and native clarify records it in the native
specification. In that case these controls apply:

1. Record the working state: `git branch --show-current` and `git status --short`.
2. Change only the native specification file, and only the sections the supplied
   answers resolve. Do not edit unrelated requirements.
3. Run `git diff --check` and read the complete diff.
4. Confirm no assumption was converted into a decision and no unresolved question
   was silently closed.
5. Report validation performed and validation not performed.
6. Before any owner-authorized commit: stage explicit paths, run
   `git diff --cached --name-only` and `git diff --cached --check`, read the
   complete staged diff, scan for sensitive data, and report the working-tree
   state.

Prohibited: `git add -A` without reviewing the staged list; destructive
cleanup; discarding work that is not yours to discard; and any commit, push,
merge, tag, publication, deployment, branch deletion, or approval without
explicit owner authorization. Recovery must be non-destructive.

### Clarification controls

Ask only questions that materially affect scope, behavior, failure handling, security, compatibility, migration, operations, or verification. Record only answers explicitly provided or confirmed by the Project Owner. If an Approved specification needs material change, stop and use controlled specification change.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Specification Clarification.
Purpose: Find ambiguity, contradiction, hidden assumptions, boundary cases, unclear failure behaviour, security uncertainty, and untestable requirements in a specification.
Mode: Read-only by default; native clarify may write answers the owner gives.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Native constitution, Product requirements, Central manual chapter 06.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/07-specification-clarification.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Question list grouped by category with impact; Recorded answers and affected requirement IDs.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
