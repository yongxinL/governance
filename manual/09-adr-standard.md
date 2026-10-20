# 09. ADR Standard

**Part II** · Owns: ADR triggers, boundaries, metadata, statuses, immutability in meaning, supersession, alternatives, rationale, consequences, relationship to RFCs, specifications, and architecture.

## 9.1 Triggers

Write an ADR for a significant, durable technical decision: technology or platform selection, data storage and schema strategy, integration patterns, security architecture, deployment topology, cross-cutting conventions, or any decision costly to reverse. Do not write ADRs for routine implementation choices contained in one feature plan.

## 9.2 Boundaries

One decision per ADR. An ADR records the decision, its context, alternatives, rationale, and consequences. It does not contain requirements (specification), proposals still under evaluation (RFC), or procedures (runbook).

## 9.3 Location, identifier, metadata

- Path: `docs/architecture/adr/ADR-NNN-<kebab-title>.md`
- Template: [`adr-template.md`](../project-template/docs/templates/adr-template.md)
- Metadata: ID, title, status, owner, created, updated; approval and supersession fields where applicable ([chapter 16](16-metadata-naming-and-status.md)).

## 9.4 Statuses

`Proposed` -> `Accepted` | `Rejected`; `Accepted` -> `Deprecated` | `Superseded`.

## 9.5 Immutability in meaning

Once Accepted, an ADR's decision and rationale are never rewritten. Permitted edits: link repair, typographical correction, and status or supersession fields. A changed decision requires a new ADR that supersedes the old one; both record the relationship (`supersedes`, `superseded_by`).

## 9.6 Alternatives, rationale, consequences

At least two credible alternatives (including "do nothing" where relevant) with honest trade-offs. Consequences include positive, negative, and follow-up obligations. Validation describes how the decision will be confirmed in practice.

## 9.7 Relationships

- An accepted RFC frequently produces one or more ADRs.
- Specifications and plans reference constraining ADRs by ID.
- `docs/architecture/README.md` summarizes the current architecture and links ADRs; it does not restate them.

## 9.8 Review

Use prompt [10](../prompts/10-adr-review.md). Acceptance is owner-controlled.
