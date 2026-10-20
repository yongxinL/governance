# ADR-NNN: <Decision title>

> **Template (non-authoritative).** Copy to `docs/architecture/adr/ADR-NNN-<kebab-title>.md`, allocate NNN in the ADR index. One decision per ADR. Once Accepted, the decision and rationale are never rewritten; supersede instead.

| Field | Value |
|---|---|
| ID | ADR-NNN |
| Title | |
| Status | Proposed |
| Owner | project-owner |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |
| Approved by / mode / date | *Completed on acceptance* |
| Supersedes | *Optional: ADR-NNN* |
| Superseded by | *Completed if superseded* |
| Related | *Optional: RFC-NNN, SPEC-NNN, INV-NNN* |

## Context (Mandatory)
*The forces at play: requirements, constraints, current state, and why a decision is needed now.*

## Decision drivers (Mandatory)
*The forces that made a decision necessary: constraints, deadlines, risk,
compatibility, cost, or prior commitments. Drivers are stated before options.*

## Decision (Mandatory)
*The decision in one or two sentences, stated actively ("We will ...").*

## Alternatives considered (Mandatory)

| Option | Benefits | Drawbacks | Reason not chosen |
|---|---|---|---|
| *Chosen option* | | | n/a |
| *Alternative, including do nothing where relevant* | | | |

## Rationale (Mandatory)
*Why the chosen option best satisfies the context.*

## Consequences (Mandatory)
- **Positive:**
- **Negative:**
- **Follow-up obligations:** *specifications, tasks, runbooks, or migrations required*

## Risks (Optional)
*Risks introduced and their mitigations.*

## Validation (Mandatory)
*How this decision will be confirmed in practice. Do not claim validation has
occurred unless it has; an unperformed check is `NOT_RUN`.*

## Evidence and links (Mandatory where any)
*Specification baselines, incidents, measurements, or prior ADRs that constrain or
inform this decision.*

## Boundaries

One durable decision per ADR. An ADR does not contain requirements, a proposal
still under evaluation, or an operational procedure; those belong to
specifications, RFCs, and runbooks.

Project ADR identifiers are unrelated to the central governance historical
`D1`-`D20` decision labels and to central `DEC-NNN` maintenance records. Never
renumber an existing ADR: a changed decision requires a new ADR that supersedes
the old one, and both keep their identifiers.
*How we will know the decision works in practice, and when to revisit it.*
