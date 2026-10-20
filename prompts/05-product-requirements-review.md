# Prompt 05: Product Requirements Review

**Mode:** Read-only · **Owning manual chapter:** [08](../manual/08-product-requirements-standard.md)

## Purpose
Review product vision and requirements for problem, users, goals, non-goals, requirements, constraints, success measures, missing behaviour, and technical leakage.

## Mode
Read-only.

## Required inputs
- `docs/product/vision.md`
- `docs/product/requirements.md`

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 08

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- Product intent belongs to the owner; reviewers raise questions.

## Permitted actions
- Identify gaps, contradictions, unmeasurable success measures, and technical leakage.
- Suggest wording.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Adding product facts or goals not stated by the owner.
- Editing the documents.

## Stop conditions
Stop and report to the Project Owner when:
- Documents are still templates with no project content.

## Expected output
- Findings table by section with severity
- Questions for the owner
- Leakage list with suggested relocation (plan or ADR)

## Owner decisions required
- Answers to questions
- Approval of product intent

## Validation criteria
- Every mandatory section assessed

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Product Requirements Review.
Purpose: Review product vision and requirements for problem, users, goals, non-goals, requirements, constraints, success measures, missing behaviour, and technical leakage.
Mode: Read-only.
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 08.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/05-product-requirements-review.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Findings table by section with severity; Questions for the owner; Leakage list with suggested relocation (plan or ADR).
End with the list of decisions required from the Project Owner.
```
