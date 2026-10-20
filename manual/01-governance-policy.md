# 01. Governance Policy

**Part I: Governance foundation** · **Owns:** purpose, scope, applicability, principles, authority, precedence, solo-owner default, foundational non-exception controls.

## 1.1 Purpose

Nexora Governance makes project intent, decisions, and evidence durable, discoverable, and controlled, so that a Project Owner and AI coding agents can work on a project over years without losing truth or creating competing versions of it.

## 1.2 Scope

This policy governs every Nexora project that has adopted a Nexora Governance release: its documentation, specifications, decisions, plans, tasks, tests and evidence, releases, operational records, agent instructions, and developer tooling.

## 1.3 Applicability

- Applies from the moment a project records an adoption state other than `Not Adopted` in `docs/governance/governance-adoption.md`.
- Applies to humans and AI agents equally; agents are bound through `AGENTS.md` ([chapter 18](18-ai-agent-standard.md)).
- Projects in `Adoption in Progress` apply it to new work immediately and to legacy content through the migration plan ([chapter 28](28-archive-retention-and-migration.md)).

## 1.4 Governance principles

1. **Repository as durable memory.** Committed artifacts, indexes, and Git history are the project's memory. Chat transcripts, agent memory, tool indexes, and personal notes are not.
2. **Single source of truth.** Every information category has one authoritative location, recorded in the source-of-truth register ([chapter 17](17-indexing-traceability-and-source-of-truth.md)).
3. **Specification before material implementation.** Material behaviour change is specified and approved before implementation ([chapter 06](06-specification-driven-development.md)).
4. **Native workflow ownership.** GitHub Spec Kit owns the SDD workflow and its artifacts ([chapter 07](07-spec-kit-standard.md)).
5. **Human authority.** Material approvals are made by the Project Owner ([chapter 05](05-lifecycle-ownership-and-approvals.md)).
6. **Proportionality.** Process scales with risk and materiality ([chapter 03](03-document-taxonomy-and-boundaries.md)).
7. **Least privilege.** Tools receive only the access they need ([chapter 20](20-developer-tooling-and-security.md)).
8. **No silent change.** Approved content is changed only through an approved, visible change.
9. **Preservation.** Historical decisions and artifacts remain recoverable in their canonical locations.

## 1.5 Governance authority

| Authority | Holder |
|---|---|
| Central governance content | Maintainer of the central governance repository (the Nexora owner) |
| Adoption of a release in a project | Project Owner |
| Project governance records | Project Owner |
| Approval of material artifacts | Project Owner |
| Workflow mechanics | GitHub Spec Kit, as configured at the pinned version |
| Implementation | Primary agent or human, under authorization |
| Supporting analysis | Tools and secondary agents (non-authoritative) |

## 1.6 Policy precedence

When sources conflict, apply this order:

1. Foundational non-exception controls (section 1.8).
2. The adopted central Nexora Governance release.
3. Project governance records (`docs/governance/`) and approved project exceptions.
4. The approved native Spec Kit constitution.
5. Approved product requirements, specifications, accepted ADRs, and accepted RFCs, each within its boundary.
6. `AGENTS.md` and nested `AGENTS.md` files (operational only; they cannot weaken anything above).
7. Plans, tasks, and supporting documents.
8. Tool output, AI output, and external documentation (never authoritative).

A conflict not resolved by this order is escalated to the Project Owner and recorded.

## 1.7 Solo-owner default

The default governance mode is `solo`. One Project Owner may perform all review functions. The approval model and the conditions for collaborative expansion are owned by [chapter 05](05-lifecycle-ownership-and-approvals.md).

## 1.8 Foundational non-exception controls

No ordinary exception ([chapter 04](04-governance-versioning-and-exceptions.md)) may bypass these controls:

| Control | Rule |
|---|---|
| NX-1 Source-of-truth integrity | No competing authoritative location for any information category. |
| NX-2 Secret handling | Credentials and sensitive data are never committed, prompted, or exposed to unapproved tools. |
| NX-3 Human approval authority | AI agents and tools cannot provide required owner approval. |
| NX-4 Durable repository memory | Decisions and approvals are recorded in the repository, not only in conversation. |
| NX-5 No silent specification change | Approved specifications change only through an approved change. |
| NX-6 No invented decisions or approvals | No artifact may claim a decision, approval, or fact that did not occur. |

A breach of an NX control is a critical finding ([chapter 29](29-audit-conformance-and-maturity.md)) and a blocking finding for release ([chapter 26](26-validation-and-quality-gates.md)).
