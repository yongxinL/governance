# Prompt 22: Governance Conformance Audit

**Mode:** Read-only  
**Owning manual chapter:** [29](../manual/29-audit-conformance-and-maturity.md)

## Purpose
Perform a read-only domain assessment to determine adoption state, control gaps, critical findings, exceptions, optional maturity, and recommended actions.

## Mode
Read-only.

## Required inputs
- Repository at a recorded commit
- Audit trigger

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 29
- `docs/governance/` records

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The audit recommends; it does not reorganize.

### Evidence and result rules

- Cite repository-relative evidence paths for every material finding.
- Use `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE` for checks.
- `NOT_RUN` is not `FAIL`; explain why the check was not run and what is required to run it.
- Do not infer approval from file presence, test success, tool output, or conversation history.
- Report validation actually performed, validation not performed, and any environmental limitations.
- Sanitize command output and never reproduce secret or personal-data values.

## Permitted actions
- Assess each domain.
- Assess mandatory controls.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Reorganizing, moving, merging, archiving, deleting, installing, configuring, or committing.

## Stop conditions
Stop and report to the Project Owner when:
- None; report all findings, critical first.

## Expected output
- Critical findings
- Domain assessment table
- Control gaps
- Exception review
- Optional maturity assessment
- Recommended actions

## Owner decisions required
- Response to critical findings
- Adoption state

## Validation criteria
- No percentage score used
- Every domain assessed or marked Not Assessed with reason

### Finding severity

Every finding records exactly one severity:

- `BLOCKING`: breaches a foundational control (NX-1 through NX-6), a mandatory
  gate, or package integrity. Stops adoption or release until resolved. Every
  NX-1 through NX-6 breach is `BLOCKING`.
- `MAJOR`: a material governance defect that is not foundational. Resolve before
  progression, or reclassify with recorded owner rationale.
- `MINOR`: a localized weakness with no material governance impact.

Each check behind a finding uses `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or
`NOT_APPLICABLE`. A domain that was not examined is `NOT_RUN` and is never
reported as conformant. No percentage score is used, and no score may offset a
`BLOCKING` finding.

Audit evidence is scoped to a named repository version and commit. An audit of
one commit does not verify a later one.

This audit reports findings and recommendations. An auditor, including an AI
agent, never approves its own material governance change, and an audit never
substitutes for Project Owner approval.

### Audit model

Assess all ten domains: governance; product; specifications; decisions; testing and evidence; releases; operations; tooling and security; agents; indexing. Use only `NOT_APPLICABLE`, `NOT_ASSESSED`, `NEEDS_ATTENTION`, `PARTIALLY_CONFORMANT`, or `CONFORMANT`. Report NX-1 through NX-6 breaches first. Optional maturity never offsets failure of a mandatory control, and no percentage score is permitted.

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Governance Conformance Audit.
Purpose: Perform a read-only domain assessment to determine adoption state, control gaps, critical findings, exceptions, optional maturity, and recommended actions.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 29, `docs/governance/` records.
Follow the authority rules, evidence rules, permitted actions, prohibited actions, and stop conditions defined in `prompts/22-governance-conformance-audit.md` of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Critical findings; Domain assessment table; Control gaps; Exception review; Optional maturity assessment; Recommended actions.
End with: evidence reviewed; checks and commands run; checks not run; blocking items; unresolved risks; and decisions required from the Project Owner.
```
