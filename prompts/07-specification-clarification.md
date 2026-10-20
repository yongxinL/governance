# Prompt 07: Specification Clarification

**Mode:** Read-only by default; native clarify may write answers the owner gives · **Owning manual chapter:** [06](../manual/06-specification-driven-development.md)

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

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Specification Clarification.
Purpose: Find ambiguity, contradiction, hidden assumptions, boundary cases, unclear failure behaviour, security uncertainty, and untestable requirements in a specification.
Mode: Read-only by default; native clarify may write answers the owner gives.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Native constitution, Product requirements, Central manual chapter 06.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/07-specification-clarification.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Question list grouped by category with impact; Recorded answers and affected requirement IDs.
End with the list of decisions required from the Project Owner.
```
