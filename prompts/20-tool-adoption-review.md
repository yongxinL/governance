# Prompt 20: Tool Adoption Review

**Mode:** Read-only · **Owning manual chapter:** [20](../manual/20-developer-tooling-and-security.md)

## Purpose
Review a proposed tool for purpose, official source, version, scope, access, data transmission, credentials, write and destructive capability, context overhead, authority, and removal.

## Mode
Read-only.

## Required inputs
- Tool name and intended use

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- `docs/governance/approved-tooling.md`
- Central manual chapters 20-25

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Adoption requires permission in approved tooling and owner approval of the register entry.

## Permitted actions
- Research official documentation.
- Draft a register entry from the template.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Installing or enabling the tool.
- Running vendor setup scripts.

## Stop conditions
Stop and report to the Project Owner when:
- No official source.
- Tool requires production credentials or broad access.

## Expected output
- Draft register entry
- Risk summary
- Recommendation (adopt, pilot, reject)

## Owner decisions required
- Adoption decision

## Validation criteria
- Every register field completed
- Removal procedure present

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Tool Adoption Review.
Purpose: Review a proposed tool for purpose, official source, version, scope, access, data transmission, credentials, write and destructive capability, context overhead, authority, and removal.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, docs/governance/approved-tooling.md, Central manual chapters 20-25.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/20-tool-adoption-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Draft register entry; Risk summary; Recommendation (adopt, pilot, reject).
End with the list of decisions required from the Project Owner.
```
