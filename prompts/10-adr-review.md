# Prompt 10: ADR Review

**Mode:** Read-only · **Owning manual chapter:** [09](../manual/09-adr-standard.md)

## Purpose
Confirm an ADR records one significant durable technical decision and review alternatives, rationale, consequences, risk, validation, follow-up, and supersession.

## Mode
Read-only.

## Required inputs
- ADR in Proposed status

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 09
- ADR index
- Related RFCs and specifications

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Acceptance is owner-controlled; accepted ADRs are immutable in meaning.

## Permitted actions
- Assess scope, alternatives, rationale, consequences, and supersession links.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Editing an Accepted ADR's decision or rationale.
- Accepting the ADR.

## Stop conditions
Stop and report to the Project Owner when:
- The ADR contains multiple decisions or requirements.

## Expected output
- Assessment table
- Required changes
- Supersession consistency check

## Owner decisions required
- Acceptance or rejection

## Validation criteria
- Exactly one decision
- At least two credible alternatives

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: ADR Review.
Purpose: Confirm an ADR records one significant durable technical decision and review alternatives, rationale, consequences, risk, validation, follow-up, and supersession.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 09, ADR index, Related RFCs and specifications.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/10-adr-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Assessment table; Required changes; Supersession consistency check.
End with the list of decisions required from the Project Owner.
```
