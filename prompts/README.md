# Nexora Prompt Collection v1.0

22 copy-ready prompts for directing AI agents under Nexora Governance. Each prompt defines purpose, mode, inputs, required reading, authority rules, permitted and prohibited actions, stop conditions, expected output, owner decisions, and validation criteria, followed by a copy-ready block.

## Why prompts do not create authority

Prompts direct work; they do not approve it. Outputs are supporting input until the Project Owner approves the resulting artifact. Prompts support native Spec Kit workflows and never create competing specifications, plans, tasks, analysis records, completion records, or sources of truth.

## Read-only and write prompts

- **Write:** 01 (scaffold files), 06 (native specification), 08 (investigation), 14 (implementation), 21 (handoff file). Prompt 07 writes owner answers only; 12 and 17 may let native commands write their native output.
- **Read-only:** all others.

## Index

| # | Prompt | Mode | Supports native Spec Kit stage | Owner decisions |
|---|---|---|---|---|
| [01](01-new-project-bootstrap.md) | New Project Bootstrap | Write | No | Primary agent; Values for unresolved markers; Approval to commit the scaffold baseline |
| [02](02-existing-project-read-only-audit.md) | Existing Project Read-Only Audit | Read-only | No | Authority for each conflicting category; Treatment of sensitive findings |
| [03](03-governance-migration-plan.md) | Governance Migration Plan | Read-only | No | Every item in the owner-decision class; Approval of the map |
| [04](04-governance-adoption-review.md) | Governance Adoption Review | Read-only | No | Adoption state; Acceptance of any exception |
| [05](05-product-requirements-review.md) | Product Requirements Review | Read-only | No | Answers to questions; Approval of product intent |
| [06](06-specification-draft.md) | Specification Draft | Write | Yes | Answers to open questions; Move to In Review and approval |
| [07](07-specification-clarification.md) | Specification Clarification | Read-only by default | Yes | Every material question |
| [08](08-investigation.md) | Investigation | Write | No | Decision on the recommendation, recorded in the appropriate artifact |
| [09](09-rfc-review.md) | RFC Review | Read-only | No | Outcome |
| [10](10-adr-review.md) | ADR Review | Read-only | No | Acceptance or rejection |
| [11](11-plan-review.md) | Plan Review | Read-only | Yes | Plan approval |
| [12](12-task-traceability-analysis.md) | Task Traceability Analysis | Read-only | Yes | Acceptance of gaps or task changes |
| [13](13-pre-implementation-gate.md) | Pre-Implementation Gate | Read-only | No | Implementation authorization |
| [14](14-implementation.md) | Implementation | Write | Yes | Deviation dispositions |
| [15](15-ponytail-quality-review.md) | Ponytail Quality Review | Read-only | No | Disposition of each finding |
| [16](16-test-and-evidence-review.md) | Test and Evidence Review | Read-only | No | Acceptance of gaps or known deviations |
| [17](17-convergence-review.md) | Convergence Review | Read-only | Yes | Acceptance of convergence and status transition |
| [18](18-release-readiness.md) | Release Readiness | Read-only | No | Release approval |
| [19](19-documentation-validation.md) | Documentation Validation | Read-only | No | Disposition of major findings |
| [20](20-tool-adoption-review.md) | Tool Adoption Review | Read-only | No | Adoption decision |
| [21](21-agent-switch-handoff.md) | Agent Switch Handoff | Write | No | Decisions listed in the handoff; Primary-agent change in the adoption record |
| [22](22-governance-conformance-audit.md) | Governance Conformance Audit | Read-only | No | Response to critical findings; Adoption state |

## Use

Copy the "Copy-ready prompt" block into the agent session. The agent must be able to read the full prompt file in the adopted governance release (or a local copy supplied for the session). Owning chapters: [manual index](../manual/README.md).
