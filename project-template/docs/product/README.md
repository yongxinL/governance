# Product Documentation

## Purpose

This area owns product vision and product requirements.

## Authority

`vision.md` and `requirements.md` are authoritative for product intent and
product-level requirements. They do not restate the central manual, and they do
not duplicate native feature specifications. They are separate
information categories with separate authoritative files.

| Artifact | Authoritative for | Template |
|---|---|---|
| `vision.md` | Problem, users, outcomes, value, principles, non-goals, constraints | [vision-template.md](vision-template.md) |
| `requirements.md` | Scope, users and use cases, functional and non-functional requirements, dependencies, risks | [requirements-template.md](requirements-template.md) |

## Triggers

Create `vision.md` when adopting a project or when product intent changes
materially. Create `requirements.md` once the vision is stable enough to state
product-level outcomes. Update either when the Project Owner approves a change.

These artifacts are distinct. Merging them, or recording either only inside a
specification, breaks the one-source-of-truth rule.

## Boundaries

Product documents describe outcomes, users, constraints, and non-goals. They must
not duplicate native feature specifications, plans, tasks, or acceptance criteria,
which live under `specs/` and are owned by GitHub Spec Kit. Technical design
belongs in plans and ADRs.

## Truthful empty state

Before product definition begins, this area may contain only these two templates.
That is the truthful state, not a missing artifact. Do not create placeholder
vision or requirement content, and never invent product facts: leave unresolved
values as explicit markers until the Project Owner supplies them.

## Approval

Approval fields are completed only from a real Project Owner decision. A drafted
product document is not an approved one.
