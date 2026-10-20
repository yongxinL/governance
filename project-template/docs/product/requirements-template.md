# Product Requirements - <PROJECT_NAME>

> **Template (non-authoritative).** Copy to `docs/product/requirements.md`. Product requirements describe capabilities and outcomes, not feature behaviour detail (native specifications) or technical design (plans and ADRs).

| Field | Value |
|---|---|
| Title | Product Requirements |
| Status | Draft |
| Owner | project-owner |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |
| Approved by / mode / date | *Completed on approval* |
| Vision | `vision.md` |

## 1. Scope (Mandatory)
*What this requirements set covers.*

## 2. User groups and key journeys (Mandatory)
*For each user group, the journeys the product must support.*

## 3. Product requirements (Mandatory)

| Label | Requirement (capability or outcome) | Priority | Rationale | Specified by |
|---|---|---|---|---|
| PR-001 | *Example (illustrative only): Users can export their records in an open format.* | Must | *Why* | *SPEC-NNN once specified* |

*Priorities: Must, Should, Could. Labels are local references only.*

## 3a. Non-functional product requirements (Mandatory)

*Product-level quality expectations. Express the outcome, not the mechanism. The
feature-level NFRs live inside the native specification as `SPEC-NNN-NFR-NNN`.*

| Label | Quality attribute | Expected outcome (no mechanism) | Verified by |
|---|---|---|---|
| PNFR-001 | *e.g. Performance, Accessibility, Privacy, Reliability* | *Observable expectation* | *SPEC-NNN-NFR-NNN once specified* |

## 3b. Dependencies (Mandatory)
*Other products, systems, teams, or external obligations this requirements set
depends on. Distinguish a true dependency from an assumption.*

## 4. Constraints (Mandatory)
*Product-level constraints. Technology appears here only if it is itself a product constraint.*

## 5. Non-goals (Mandatory)
*Explicit exclusions.*

## 6. Success measures (Mandatory)
*Observable measures linked to the vision goals.*

## 6a. Risks (Mandatory)
*Product risks with likelihood and impact, and the intended mitigation or the
decision still owed by the Project Owner.*

## 7. Assumptions (Optional)
*Assumptions to validate, each with how it will be validated. An assumption that
has not been validated stays listed here; do not promote it to a requirement.*

## 8. Open questions (Optional)

| Question | Raised | Decision needed by | Resolution |
|---|---|---|---|

## 9. Traceability to specifications (Mandatory)
*Map each product requirement to the native specification that carries it, once
that specification exists. Until then, leave the target blank and truthful.*

| Requirement | Native specification | Acceptance criteria |
|---|---|---|
| PR-001 | *SPEC-NNN once specified* | *SPEC-NNN-AC-NNN once specified* |

## 10. Boundaries

This document states product-level outcomes. It must not contain feature
behaviour detail, acceptance criteria owned by a specification, technical design,
plans, or task lists. Those belong to native Spec Kit artifacts under `specs/`
and to ADRs.

## 11. Change history
*Material changes after approval: date, change, approval mode.*
