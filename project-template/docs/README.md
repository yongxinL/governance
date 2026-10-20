# Project Documentation

The documentation tree is governed by the adopted Nexora Governance release
(recorded in [governance/governance-adoption.md](governance/governance-adoption.md)).
This file is the root index. Each area index defines purpose, authority, artifact
triggers, and current entries.

Empty indexes remain truthful and do not require placeholder artifacts. The
presence of this tree does not mean the project has adopted governance; only a
recorded Project Owner approval does.

## Areas

| Area | Index | Contains |
|---|---|---|
| Governance | [governance/README.md](governance/README.md) | Adoption, source of truth, exceptions, tooling |
| Product | [product/README.md](product/README.md) | Vision and product requirements |
| Architecture | [architecture/README.md](architecture/README.md) | Architecture overview, justified delivery plans |
| ADRs | [architecture/adr/README.md](architecture/adr/README.md) | Architecture decision records |
| RFCs | [rfc/README.md](rfc/README.md) | Material proposals under evaluation |
| Investigations | [investigations/README.md](investigations/README.md) | Evidence-gathering inquiries |
| Testing | [testing/README.md](testing/README.md) | Project-wide test strategy and evidence |
| Operations | [operations/README.md](operations/README.md) | Operational model |
| Runbooks | [operations/runbooks/README.md](operations/runbooks/README.md) | Operational procedures |
| Releases | [releases/README.md](releases/README.md) | Release records |
| Lessons | [lessons/README.md](lessons/README.md) | Lessons until incorporated or retired |
| Archive | [archive/README.md](archive/README.md) | Displaced and retired documentation only |
| Templates | [templates/README.md](templates/README.md) | Non-authoritative templates |

Every governed area keeps a substantive README index. An area index is never
removed, even when the area is empty.

## Authority in this tree

- **Indexes** are authoritative for identity, identifier allocation, location,
  status, supersession, and baseline reference.
- **Linked artifacts** are authoritative for complete content: requirements,
  decisions, rationale, procedures, and evidence.
- **Templates** are non-authoritative starting points. A template is never a
  record of a decision, approval, or result that occurred.
- **Native Spec Kit artifacts** are authoritative for specifications, feature
  plans, tasks, and analyses, and live outside this tree.

Consult [governance/source-of-truth-register.md](governance/source-of-truth-register.md)
before creating any document. Create artifacts only when their governance
trigger applies. Update the relevant area index in the same commit as the
artifact.

## Specifications and native content

Specifications, feature plans, tasks, and analyses are owned by GitHub Spec Kit
under `.specify/` and `specs/`, created at approved Spec Kit initialization. They
are not duplicated here.

Their index is `specs/README.md`, created only after confirming the installed
Spec Kit version tolerates a non-feature file in `specs/`. If it does not,
maintain the specification index in this file instead and record the reason in
[governance/documentation-exceptions.md](governance/documentation-exceptions.md).

The project's principles live in the native Spec Kit constitution, not in this
tree.
