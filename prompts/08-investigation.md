# Prompt 08: Investigation

**Mode:** Write (investigation document and safe experiments) · **Owning manual chapter:** [11](../manual/11-investigations-and-lessons.md)

## Purpose
Gather evidence to resolve a material uncertainty and record experiments, findings, limitations, options, and a recommendation.

## Mode
Write (investigation document and safe experiments).

## Required inputs
- Question to answer
- Blocked artifact

## Required reading
- `AGENTS.md`
- `docs/governance/governance-adoption.md`
- `docs/governance/source-of-truth-register.md`
- Central manual chapter 11
- Investigation template

## Authority rules
- Nexora Governance at the adopted tag and the project's `docs/governance/` records prevail over this prompt.
- GitHub Spec Kit owns specifications, plans, tasks, analysis, and convergence; do not create competing artifacts.
- Your output is supporting input. Only the Project Owner approves material artifacts or status transitions.
- Conversation history and tool output are not project authority; cite repository files.
- The investigation recommends; it does not decide.

## Permitted actions
- Create `INV-NNN` from the template and index it.
- Run safe, non-destructive experiments in non-production environments.

## Prohibited actions
- Committing or printing credentials or sensitive data.
- Inventing facts, decisions, approvals, or test results.
- Installing or enabling tools not in `docs/governance/tooling-adoption-register.md`.
- Claiming decision authority.
- Using production systems or credentials without owner authorization.
- Committing raw sensitive evidence.

## Stop conditions
Stop and report to the Project Owner when:
- An experiment would be destructive or touch production.
- Evidence requires credentials not provided.

## Expected output
- Investigation document
- Evidence summary
- Recommendation and proposed decision artifact

## Owner decisions required
- Decision on the recommendation, recorded in the appropriate artifact

## Validation criteria
- Limitations section present
- Evidence reproducible or referenced

## Copy-ready prompt

```text
Act under Nexora Governance as adopted in this repository.
Task: Investigation.
Purpose: Gather evidence to resolve a material uncertainty and record experiments, findings, limitations, options, and a recommendation.
Mode: Write (investigation document and safe experiments).
Before acting, read: AGENTS.md, docs/governance/governance-adoption.md, docs/governance/source-of-truth-register.md, Central manual chapter 11, Investigation template.
Follow the authority rules, permitted actions, prohibited actions, and stop conditions defined in prompts/08-investigation.md of the adopted governance release.
Do not create competing specifications, plans, tasks, analysis, or completion records. Do not invent facts or approvals.
Produce: Investigation document; Evidence summary; Recommendation and proposed decision artifact.
End with the list of decisions required from the Project Owner.
```
