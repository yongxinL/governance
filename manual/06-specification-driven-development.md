# 06. Specification-Driven Development

**Part II** · **Owns:** SDD principles, behaviour-change triggers, specification authority, stable requirement identifiers, controlled specification change, requirement-to-evidence lifecycle, no competing workflow owners.

## 6.1 Principles

1. Observable behaviour is specified before it is materially built or changed.
2. Specifications describe **what** and **why**; plans describe **how**.
3. Every material requirement is identifiable, testable, and traceable to evidence.
4. Ambiguity is resolved explicitly, not by assumption.
5. One workflow owner: GitHub Spec Kit ([chapter 07](07-spec-kit-standard.md)).

## 6.2 When a specification is required

A specification is required for: new observable behaviour; materially changed observable behaviour; new product functionality; material business-rule changes; material interface changes; security-sensitive features; migration-sensitive changes; complex behavioural defects; changes with multiple acceptance criteria; other material scope requiring governed behaviour.

A full specification is not normally required for: typographical corrections, formatting, mechanical cleanup, behaviour-preserving refactoring, routine test improvements, minor configuration correction, routine compatible dependency updates. Simple single-cause defects may use the Spec Kit `bug` extension within limits B1-B9 ([chapter 07](07-spec-kit-standard.md#77-spec-kit-bug-extension)).

When in doubt, the Project Owner decides and the decision is noted in the commit or pull request.

## 6.3 Specification authority

The approved native Spec Kit specification is the sole authority for a feature's behaviour, requirements, and acceptance criteria. No Nexora-format specification file exists. Product requirements provide intent; ADRs constrain design; neither replaces the specification.

## 6.4 Stable identifiers

Each specification receives a project-local `SPEC-NNN`, recorded in the specification content and in `specs/README.md`. Requirements inside it use `SPEC-NNN-FR-NNN`, `SPEC-NNN-NFR-NNN`, and `SPEC-NNN-AC-NNN`. Native Spec Kit directory and file names remain native. Allocation rules are owned by [chapter 16](16-metadata-naming-and-status.md).

## 6.5 Controlled specification change

- Draft and In Review specifications may be edited freely.
- Approved and later specifications change only through an owner-approved change: record what changed, why, impact on plan, tasks, tests, and release, and update the approval fields. Re-run clarification and analysis where the change is material.
- Removed requirements keep their identifiers, marked withdrawn; identifiers are never reused.
- Agents must stop and report when implementation reveals that the specification is wrong (NX-5).

## 6.6 Requirement-to-evidence lifecycle

```
Product intent -> SPEC-NNN (FR/NFR/AC) -> native plan -> native tasks
  -> implementation -> tests and evidence (mapped to AC/NFR)
  -> native convergence -> release record (baseline references)
```

Each acceptance criterion is mapped to evidence or explicitly marked not applicable with a reason ([chapter 13](13-testing-evidence-and-verification.md)).

## 6.7 Existing projects

Existing projects do not retrospectively specify the whole system. Specify incrementally, prioritizing active changes, security-sensitive functionality, external interfaces, complex business rules, frequently defective areas, poorly understood behaviour, and operationally critical components. Distinguish observed, intended, and approved future behaviour explicitly.

## 6.8 No competing workflow owners

GitHub Spec Kit owns `.specify/`, `specs/`, and the native specification, plan,
task, analysis, and convergence artifacts. Do not run a second SDD framework,
planning tool, or task tracker as an authority for the same work, and do not
reproduce native artifacts under `docs/`. External issue trackers may mirror
tasks for visibility; the native tasks artifact remains authoritative.

## 6.9 Agent conduct at gates

Agents stop at every approval gate defined by
[chapter 05](05-lifecycle-ownership-and-approvals.md) and wait for the Project
Owner. An agent proposes; the Project Owner approves.

Validation that could not be performed is reported as not run, never as passed.
A check outcome distinguishes `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, and
`NOT_APPLICABLE`; an absent or unexecuted check is `NOT_RUN` and must not be
presented as a success. Rules: [chapter 26](26-validation-and-quality-gates.md).
