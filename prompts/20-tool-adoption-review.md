# Prompt 20: Tool Adoption Review

**Mode:** Read-only  
**Owning manual chapter:** [20](../manual/20-developer-tooling-and-security.md)

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

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

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

### Tool-state model

Distinguish permission from lifecycle and task authorization:

- `approved-tooling.md` determines whether use is permitted;
- the register state is `Planned`, `Pilot`, `Enabled`, `Disabled`, or `Removed`;
- authorization for the current operation is a separate owner decision.

Assess classification, provenance, pinning, installer effects, project paths, network targets, external transmission, credentials, write and destructive capability, persistence, context overhead, failure behavior, approval, review trigger, removal criteria, and complete removal procedure. Do not run vendor installers or setup scripts.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Tool Adoption Review.
Purpose: Review a proposed tool for purpose, official source, version, scope, access, data transmission, credentials, write and destructive capability, context overhead, authority, and removal.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, docs/governance/approved-tooling.md, Central manual chapters 20-25.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/20-tool-adoption-review.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Draft register entry; Risk summary; Recommendation (adopt, pilot, reject).
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
