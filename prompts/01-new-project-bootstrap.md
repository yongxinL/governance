# Prompt 01: New Project Bootstrap

**Mode:** Write (governance scaffold files only) · **Owning manual chapter:** [30](../manual/30-adoption-playbook.md)

## Purpose
Copy and customize the full Nexora scaffold into a new project, establish adoption metadata, configure approved environment examples, and prepare for native Spec Kit initialization.

## Mode
Write (governance scaffold files only).

## Required inputs
- Central governance checkout at tag `v1.0.0`
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

## Validation criteria
- All scaffold files present including `.codex/`
- No `.specify/` or `specs/` created by this prompt
- All MCP servers disabled
- No invented facts

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: New Project Bootstrap.
Purpose: Copy and customize the full Nexora scaffold into a new project, establish adoption metadata, configure approved environment examples, and prepare for native Spec Kit initialization.
Mode: Write (governance scaffold files only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central `instructions/README.md, Central manual chapters 02, 07, 20, 30, project-template/ADOPTION-INSTRUCTIONS.md.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/01-new-project-bootstrap.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: List of files created; Table of markers replaced and markers remaining with reason; Proposed `specify init` command; Proposed commit message (example).
End with the list of decisions required from the Project Owner.
```
