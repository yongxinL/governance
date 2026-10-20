# Delivery Plan: <Initiative title>

> **Template (non-authoritative).** Copy to `docs/architecture/delivery-plan-<kebab-title>.md`. Use only when one native feature plan is insufficient. This plan coordinates; it never contains feature tasks or restates requirements.

| Field | Value |
|---|---|
| Title | |
| Status | Draft |
| Owner | project-owner |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |
| Approved by / mode / date | *Completed on approval* |
| Trigger | Multiple specifications / multiple releases / multiple systems / governance adoption / infrastructure transition / data migration / coordinated deprecation / other (state) |

## 1. Objective (Mandatory)

## 2. Participating work (Mandatory)

| Item | Type (SPEC, release, system, RFC) | Native plan location | Status |
|---|---|---|---|

## 3. Dependencies and order (Mandatory)

## 4. Milestones and owner checkpoints (Mandatory)

| Milestone | Entry criteria | Exit criteria | Owner checkpoint |
|---|---|---|---|

## 5. Migration and rollback windows (Mandatory where applicable)

## 6. Risks (Mandatory)

## 7. Communication and coordination (Optional)

## 8. Integration points (Mandatory)
*Interfaces, data flows, and shared components touched across the participating
work, and their owners.*

## 9. Compatibility and migration (Mandatory where applicable)
*Data, interface, and configuration compatibility across the coordinated
releases, and the ordered migration steps.*

## 10. Operational readiness (Mandatory where applicable)
*Deployment, monitoring, rollback, and support readiness each participating
release requires before the whole sequence can proceed.*

## 11. Validation and evidence (Mandatory)
*How the coordinated outcome is verified. Use canonical outcomes `PASS`, `FAIL`,
`BLOCKED`, `NOT_RUN`, `NOT_APPLICABLE`; an unperformed check is `NOT_RUN`.*

## 12. Release coordination (Mandatory)
*Sequencing of releases, and what must be true before each one ships.*

## 13. Decisions required (Mandatory)
*Choices reserved for the Project Owner, left unresolved until actually made.*

## 14. Boundaries

This plan coordinates work across specifications and systems. It does not replace
or override any native feature plan, does not restate feature requirements, and
contains no competing feature task list. Each participating feature keeps its own
native plan and tasks under `specs/`. Where this plan and a native plan disagree,
the native plan governs.

## 15. Completion criteria (Mandatory)
*When this plan is complete; completion of each feature remains with its native convergence.*
