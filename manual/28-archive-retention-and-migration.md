# 28. Archive, Retention, and Migration

**Part VI** · **Owns:** canonical retention, archive triggers, legacy documentation, existing-project audit, authority-first migration, safe changes, careful consolidation, owner decisions, sensitive deletion, migration completion.

## 28.1 Canonical retention

Completed ADRs, RFCs, investigations, specifications, lessons, and releases stay in their canonical locations with terminal statuses. Completion is not an archive trigger. Retention is lifecycle-based, not a fixed time period.

## 28.2 Archive triggers

Use `docs/archive/` for: legacy documentation displaced during migration, retired documentation sets, obsolete formats, and historical material that no longer belongs in an active area. Each archived item is listed in `docs/archive/README.md` with origin path, date, reason, and replacement link.

### 28.2.1 The archive is not a second source of truth

`docs/archive/` preserves history; it never holds live authority. An archived
artifact keeps its original identifier, its terminal status, and a link to its
replacement. Nothing in the archive may be cited as current policy, and a
conflict between an archived document and an active one is always resolved in
favour of the active document.

Archived content is not edited to reflect current policy. It is preserved as it
was, with corrections limited to link repair and an explicit correction note.
Superseded content is distinguished from obsolete content: superseded material
still has a live successor, obsolete material simply no longer applies.

### 28.2.2 Retention and removal authority

- Historical decisions and their identifiers are retained permanently. Accepted
  ADRs and released records are never deleted to tidy an area.
- Every removal, whether deletion or archival, is recorded with its reason and
  requires owner authority. An unresolved question or an open conflict is never
  resolved by deletion.
- Evidence supporting a released record is retained with it.
- Audit history is preserved. Rewriting published history is not an archival
  strategy.

Migration is required only by substantive governance change, never because
documentation wording, formatting, or examples were improved. A corrective
documentation release creates no migration obligation for adopting projects.

## 28.3 Existing-project audit

Read-only (prompt [02](../prompts/02-existing-project-read-only-audit.md)). Inventory governed documentation, other formats, configuration with embedded operational authority, CI workflows, API schemas, environment examples, deployment definitions, decision-bearing source comments, and existing tool and agent instructions. For each item record purpose, audience, type, status, authority, owner if known, current or historical, duplicates, conflicts, broken links, orphans, missing indexes, embedded requirements and decisions, specification coverage, and recommended action. Do not inventory every source file individually.

## 28.4 Authority first

Resolve source-of-truth conflicts and record the outcome in the register before moving, merging, rewriting, archiving, or deleting anything.

## 28.5 Migration map classes

| Class | Examples | Approval |
|---|---|---|
| Safe automatic | Add indexes, fix broken relative links, add metadata to unambiguous documents, move a document whose category is certain (with link repair) | Batch approval of the map |
| Careful consolidation | Merge duplicates, split mixed documents, normalize ADRs and RFCs, register existing specifications | Per item review |
| Owner decision | Conflicting authorities, unclear current behaviour, deletions, archive of possibly current content | Explicit owner decision |

Use prompt [03](../prompts/03-governance-migration-plan.md) to produce the map.

## 28.6 Controlled batches

Suggested order: governance and indexes · safe moves and link repair · ADR and RFC normalization · specification registration · duplicate consolidation · metadata and traceability · validation · legacy archive. One batch per commit or pull request.

## 28.7 Sensitive deletion

Content containing secrets or personal data is removed from the working tree immediately, the secret rotated, and history rewriting considered by the owner; record the event without repeating the sensitive content.

## 28.8 Migration completion

Visible authority; conflicts resolved or documented; valid indexes; stable new-work process; explicit exceptions; migration findings addressed or accepted; agreed validation completed. Record the adoption state in `governance-adoption.md` ([chapter 29](29-audit-conformance-and-maturity.md)).
