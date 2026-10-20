# Prompt 04: Governance Adoption Review

**Mode:** Read-only  
**Owning manual chapter:** [29](../manual/29-audit-conformance-and-maturity.md)

## Purpose
Review adoption metadata, adopted central release, exceptions, and source-of-truth integrity, and assess readiness for Level 1: Controlled.

## Mode
Read-only.

## Required inputs
- Project repository after scaffold customization (and after Spec Kit initialization where applicable)

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapters 04, 29, 30
- `docs/governance/` records
- Native constitution

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Readiness is a recommendation; the owner sets the adoption state.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Check each Level 1 mandatory control.
- Check adoption record completeness and that the tag is immutable (not a branch).

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Changing the adoption state.
- Editing records.

## Stop conditions
Stop and report to the Project Owner when:
- The adopted reference is a branch, not a tag.
- A non-exception control breach is found.

## Expected output
- Control-by-control result table
- Domain assessments
- Exceptions review
- Recommended adoption state

## Owner decisions required
- Adoption state
- Acceptance of any exception

## Validation criteria
- All nine Level 1 controls assessed with evidence paths

### Mandatory Level 1 controls

Assess all nine controls from manual chapter 29 individually: adoption record; source-of-truth register; area indexes; `AGENTS.md`; approved native constitution; absence of competing SDD authority; absence of credentials; conditional-tool registration; and complete exception records.

Report NX-1 through NX-6 breaches first as critical findings. Recommend `Not Adopted`, `Adoption in Progress`, `Adopted with Exceptions`, or `Adopted`; only the Project Owner changes the adoption state.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Governance Adoption Review.
Purpose: Review adoption metadata, adopted central release, exceptions, and source-of-truth integrity, and assess readiness for Level 1: Controlled.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapters 04, 29, 30, `docs/governance/` records, Native constitution.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/04-governance-adoption-review.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Control-by-control result table; Domain assessments; Exceptions review; Recommended adoption state.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
