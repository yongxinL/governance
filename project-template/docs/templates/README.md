# Documentation Templates

## Purpose

This directory holds the non-authoritative starting points used to create
governed project artifacts.

## Authority

No template is authoritative. A template is never evidence that a decision,
approval, verification, or release occurred. Authority belongs to the copied
artifact in its canonical location, and only once the Project Owner has approved
what it records.

Templates in this directory are non-authoritative starting points. Copy the
applicable template to its canonical location, allocate any required identifier
in the owning index, replace guidance text, and obtain the required approval.

Do not create an artifact solely to populate the scaffold. Apply the trigger and
proportionality rules in the central manual.

Copying a template does not grant approval and does not create a record of a
decision, verification, or result. Every copied template starts unresolved: fill
approval fields only from a real Project Owner decision, and record evidence only
for validation that actually ran.

The two product templates live in `docs/product/` because their canonical targets
are in that area. All other templates live in this directory.

## Index

| Template | Canonical target | Resulting artifact |
|---|---|---|
| [../product/vision-template.md](../product/vision-template.md) | `docs/product/vision.md` | Authoritative |
| [../product/requirements-template.md](../product/requirements-template.md) | `docs/product/requirements.md` | Authoritative |
| [adr-template.md](adr-template.md) | `docs/architecture/adr/ADR-NNN-<title>.md` | Authoritative |
| [rfc-template.md](rfc-template.md) | `docs/rfc/RFC-NNN-<title>.md` | Authoritative |
| [investigation-template.md](investigation-template.md) | `docs/investigations/INV-NNN-<title>.md` | Authoritative |
| [lesson-learned-template.md](lesson-learned-template.md) | `docs/lessons/LES-NNN-<title>.md` | Authoritative |
| [release-template.md](release-template.md) | `docs/releases/<version>.md` | Authoritative |
| [runbook-template.md](runbook-template.md) | `docs/operations/runbooks/<title>.md` | Authoritative |
| [test-plan-template.md](test-plan-template.md) | Project-wide test strategy, or the native feature test-plan location | Supporting |
| [verification-summary-template.md](verification-summary-template.md) | `docs/testing/`, or the native feature location | Supporting |
| [temporary-work-handoff-template.md](temporary-work-handoff-template.md) | Temporary branch-root `HANDOFF.md` | Working state only |
| [tooling-adoption-entry-template.md](tooling-adoption-entry-template.md) | `docs/governance/tooling-adoption-register.md` | Authoritative |
| [cross-specification-delivery-plan-template.md](cross-specification-delivery-plan-template.md) | `docs/architecture/delivery-plan-<title>.md` | Authoritative |

## Triggers

| Template | Create only when |
|---|---|
| Vision, requirements | Adopting a new project, or a material change to product intent |
| ADR | A significant, durable technical decision is made or revisited |
| RFC | A material proposal needs evaluation before it can be decided |
| Investigation | Material uncertainty blocks a specification, plan, decision, or incident |
| Lesson | Durable learning arises and is not yet recorded elsewhere |
| Release | A release reaches users or production |
| Runbook | A repeatable operational procedure exists |
| Test plan | A feature or project needs an explicit test strategy |
| Verification summary | Evidence must be summarized for a scope and commit |
| Temporary handoff | Work is incomplete across an agent or session boundary |
| Tooling adoption entry | A tool is planned, piloted, enabled, disabled, or removed |
| Delivery plan | One native feature plan is insufficient to coordinate the work |

An area may remain empty. An empty area is a truthful state, not a missing
artifact.
