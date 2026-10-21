# Nexora Prompt Collection v1.0.1

**Version:** 1.0.1
**Release tag:** `v1.0.1`
**Status:** Released
**Release date:** 2026-10-21
**Prompt count:** 22

This collection belongs to released version 1.0.1.

## Purpose

This collection provides reusable, copy-ready instructions for AI agents
operating under Nexora Governance. Each prompt defines its purpose, mode,
inputs, required reading, authority rules, evidence rules, permitted and
prohibited actions, stop conditions, output, Project Owner decisions, and
validation criteria.

Prompts direct work. They do not create authority, approve artifacts, authorize
material status transitions, or replace repository evidence. The Project Owner
retains all material approval authority.

## Authority and usage

Before using a prompt:

1. Confirm the project has adopted an immutable Nexora Governance release.
2. Read root `AGENTS.md` and the project governance records.
3. Read the prompt's owning manual chapters and the applicable authoritative
   project artifacts.
4. Confirm required tools are permitted, registered, enabled, and authorized
   for the intended operation.
5. Invoke the prompt from a clean or explicitly recorded repository state.
6. Review all generated output and diffs before any commit.

The prompt file in the adopted governance release is authoritative over a copied
chat fragment. The copy-ready section is a concise launcher and assumes the
agent can read the full prompt file.

## Common result vocabulary

Use these check results consistently:

- `PASS`: requirement evidenced and satisfied.
- `FAIL`: check executed and requirement not satisfied.
- `BLOCKED`: cannot proceed because a prerequisite, decision, or safety
  condition is unresolved.
- `NOT_RUN`: check was not executed; explain why and what is required.
- `NOT_APPLICABLE`: check does not apply; provide a reason.

A check that was not run is never reported as passed or failed. `NOT_RUN` is not
`FAIL`, and `BLOCKED` is never silently treated as satisfied. An approved
deviation requires actual recorded Project Owner approval; without it, the
finding stands.

A prompt reporting a recommendation never thereby approves it. `READY` from
prompt 18, a conformant result from prompt 04, and a clean result from prompt 22
are all recommendations. Only the Project Owner approves.

Prompt text does not itself grant mutation authority. Running a write prompt
permits only the writes that prompt names, within its stated scope, and only
after the Project Owner has authorized the operation.

## Common finding severity

- `BLOCKING`: prevents gate passage or release.
- `MAJOR`: resolve before progression unless reclassified with documented owner
  rationale.
- `MINOR`: non-material wording or formatting issue.

NX-1 through NX-6 breaches are critical and blocking.

## Read-only and write behavior

### Write prompts

- 01: governance scaffold files only.
- 06: native specification and its approved index entry only.
- 08: investigation document, index entry, and safe non-production experiments.
- 14: authorized implementation scope, tests, documentation, and native task
  state.
- 21: temporary `HANDOFF.md` only.

Prompt 07 is read-only by default and may record only Project Owner answers
through the native clarification workflow. Prompts 12 and 17 may allow their
native Spec Kit commands to create native reports.

All other prompts are read-only.

## Prompt index

| # | Prompt | Mode | Native Spec Kit support | Primary owner decision |
|---:|---|---|---:|---|
| 01 | [New Project Bootstrap](01-new-project-bootstrap.md) | Write, scaffold only | No | Primary agent, unresolved markers, scaffold baseline |
| 02 | [Existing Project Read-Only Audit](02-existing-project-read-only-audit.md) | Read-only | No | Conflicting authority and sensitive findings |
| 03 | [Governance Migration Plan](03-governance-migration-plan.md) | Read-only plan | No | Migration map and owner-decision items |
| 04 | [Governance Adoption Review](04-governance-adoption-review.md) | Read-only | No | Adoption state and exceptions |
| 05 | [Product Requirements Review](05-product-requirements-review.md) | Read-only | No | Product intent and open questions |
| 06 | [Specification Draft](06-specification-draft.md) | Write, native spec | Yes | Open questions, review, and approval |
| 07 | [Specification Clarification](07-specification-clarification.md) | Read-only by default | Yes | Material clarification answers |
| 08 | [Investigation](08-investigation.md) | Write, investigation | No | Disposition of recommendation |
| 09 | [RFC Review](09-rfc-review.md) | Read-only | No | RFC outcome |
| 10 | [ADR Review](10-adr-review.md) | Read-only | No | ADR acceptance or rejection |
| 11 | [Plan Review](11-plan-review.md) | Read-only | Yes | Plan approval |
| 12 | [Task Traceability Analysis](12-task-traceability-analysis.md) | Read-only; native report allowed | Yes | Gap or task-change disposition |
| 13 | [Pre-Implementation Gate](13-pre-implementation-gate.md) | Read-only | No | Implementation authorization |
| 14 | [Implementation](14-implementation.md) | Write, authorized scope | Yes | Deviation disposition |
| 15 | [Ponytail Quality Review](15-ponytail-quality-review.md) | Read-only pilot | No | Finding disposition |
| 16 | [Test and Evidence Review](16-test-and-evidence-review.md) | Read-only | No | Evidence gaps and deviations |
| 17 | [Convergence Review](17-convergence-review.md) | Read-only; native report allowed | Yes | Convergence acceptance and status transition |
| 18 | [Release Readiness](18-release-readiness.md) | Read-only | No | Release approval |
| 19 | [Documentation Validation](19-documentation-validation.md) | Read-only | No | Major-finding disposition |
| 20 | [Tool Adoption Review](20-tool-adoption-review.md) | Read-only | No | Adoption, pilot, or rejection |
| 21 | [Agent Switch Handoff](21-agent-switch-handoff.md) | Write, handoff only | No | Handoff decisions and permanent agent switch if applicable |
| 22 | [Governance Conformance Audit](22-governance-conformance-audit.md) | Read-only | No | Critical-finding response and adoption state |

## Safety rules applying to every prompt

- Never commit, print, or reproduce credentials, private keys, tokens, cookies,
  personal data, or sensitive production data.
- Never invent facts, decisions, approvals, test results, commands, or evidence.
- Never install or enable a tool merely because it is available.
- Never create competing Spec Kit specifications, plans, tasks, analyses, or
  completion records.
- Never perform publishing, deployment, protected-branch pushes, merges, tags,
  releases, deletion, or destructive external actions without explicit owner
  authorization.
- Cite repository-relative evidence paths for material findings.
- Report checks and commands actually run, checks not run, limitations,
  blocking items, and owner decisions.

## Release maintenance

When prompts change:

1. review owning manual chapters and affected templates;
2. update this index and cross-references;
3. run documentation and link validation;
4. regenerate package derivatives and `MANIFEST.json` last;
5. validate a clean archive extraction;
6. release under a new immutable semantic version tag.
