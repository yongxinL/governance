# Prompt 06: Specification Draft

**Mode:** Write (native specification only) · **Owning manual chapter:** [06](../manual/06-specification-driven-development.md)

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

## Validation criteria
- Every AC is testable
- IDs unique and sequential
- No duplicate specification location

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Specification Draft.
Purpose: Draft a native Spec Kit specification for a material change, allocate `SPEC-NNN`, and assign stable FR, NFR, and AC identifiers.
Mode: Write (native specification only).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Native constitution, Product requirements, Constraining ADRs, Specification index, Central manual chapters 06, 07, 16.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/06-specification-draft.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Native specification path; Allocated SPEC ID; Requirement and AC list with IDs; Coverage notes for behaviour, interfaces, data, failure, security, compatibility, migration, verification, operations, rollback (or not applicable with reason); Open questions.
End with the list of decisions required from the Project Owner.
```
