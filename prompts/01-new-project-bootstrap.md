# Prompt 01: New Project Bootstrap

**Mode:** Write (governance scaffold files only)  
**Owning manual chapter:** [30](../manual/30-adoption-playbook.md)

## Purpose
Copy and customize the full Nexora scaffold into a new project, establish adoption metadata, configure approved environment examples, and prepare for native Spec Kit initialization.

## Mode
Write (governance scaffold files only).

## Required inputs
- Central governance release source. The central repository location is a
  required input supplied by the Project Owner and recorded as
  `<GOVERNANCE_REPOSITORY_URL>`. This prompt ships no default governance
  repository; if none is supplied, stop and report the missing input.
- Central governance checkout at the exact immutable release tag being adopted
- Project root path
- Known values for customization markers (project name, owner, central repository, adoption date, primary agent)
- Project test, build, and lint commands if they exist

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central `instructions/README.md`
- Central manual chapters 02, 07, 20, 30
- `project-template/ADOPTION-INSTRUCTIONS.md`

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Values not supplied remain as markers with a note in the adoption record.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Copy `project-template/` contents including hidden files.
- Replace markers with supplied values.
- Create live agent configuration from the example for the primary agent, with every MCP server disabled.
- Prepare (not run, unless instructed) the pinned `specify init` command.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Creating `.specify/` or `specs/` manually.
- Creating product, ADR, RFC, investigation, release, runbook, or lesson artifacts with invented content.
- Enabling any conditional tool.
- Committing without owner instruction.

## Stop conditions
Stop and report to the Project Owner when:
- A required value is unknown and cannot be left as a marker safely.
- The target directory already contains governance or Spec Kit files (switch to the existing-project process).
- Hidden files cannot be copied.

## Expected output
- List of files created
- Table of markers replaced and markers remaining with reason
- Proposed `specify init` command
- Proposed commit message (example)

## Owner decisions required
- Primary agent
- Values for unresolved markers
- Approval to commit the scaffold baseline

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
- All scaffold files present including `.codex/`
- No `.specify/` or `specs/` created by this prompt
- All MCP servers disabled
- No invented facts

### Package and scaffold controls

- Resolve the adopted governance version and immutable tag from the selected release; do not hard-code a release in this prompt.
- Validate the selected release against `MANIFEST.json` before copying files.
- Copy the complete contents of `project-template/`, including hidden `.codex/` content and file modes.
- If the target already contains governance, `.specify/`, `specs/`, governed documentation, or conflicting agent configuration, stop and switch to the existing-project process.
- Replace every known customization marker. Unknown values may remain only when the adoption record explains why, who owns resolution, and the follow-up required.
- Create live configuration only for the selected primary agent from its reviewed example. Remove explanatory example-only keys where required.
- Do not run `specify init` in this prompt. Prepare the pinned command as the next reviewable stage.
- Review `git status`, `git diff --check`, and the complete diff before reporting readiness.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: New Project Bootstrap.
Purpose: Copy and customize the full Nexora scaffold into a new project, establish adoption metadata, configure approved environment examples, and prepare for native Spec Kit initialization.
Mode: Write (governance scaffold files only).
Before acting, read the central release: `README.md`, `instructions/README.md`, `MANIFEST.json`, Central manual chapters 02, 07, 20, 30, project-template/ADOPTION-INSTRUCTIONS.md.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/01-new-project-bootstrap.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: List of files created; Table of markers replaced and markers remaining with reason; Proposed `specify init` command; Proposed commit message (example).
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
