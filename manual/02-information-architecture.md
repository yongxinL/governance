# 02. Information Architecture

**Part I** · Owns: central versus project governance, versioned central adoption, full project scaffold, canonical paths, native Spec Kit ownership of paths, authoritative versus supporting content, generated versus source content.

## 2.1 Central versus project governance

| Layer | Location | Contains | Does not contain |
|---|---|---|---|
| Central governance | Central repository, released by tag | Manual, instructions, templates, prompts | Project facts |
| Project governance | `docs/governance/` in each project | Adoption record, source-of-truth register, exceptions, tooling records | Copies of the manual |

Projects reference the central release; they do not copy the manual. `CENTRAL-GOVERNANCE-REFERENCE.md` in the project root is a concise pointer, not a copy.

## 2.2 Versioned central adoption

Each project adopts a specific release by recording repository, version, and immutable tag in `docs/governance/governance-adoption.md`. Projects never inherit changes from the central default branch. Upgrade procedure: [chapter 04](04-governance-versioning-and-exceptions.md) and [chapter 30](30-adoption-playbook.md).

## 2.3 Full project scaffold

Every project receives the full scaffold from `project-template/`. Every directory contains a substantive README index explaining purpose, authority, triggers, and indexing. Directory existence does not make artifact creation mandatory; an index may truthfully state that no artifacts exist yet. Nexora never pre-creates `.specify/` or `specs/`.

## 2.4 Canonical paths

| Path | Purpose | Owning chapter |
|---|---|---|
| `AGENTS.md` | Operational agent control document | 18 |
| `CENTRAL-GOVERNANCE-REFERENCE.md` | Pointer to adopted central release | 04 |
| `docs/README.md` | Documentation root index | 17 |
| `docs/governance/` | Adoption, source of truth, exceptions, tooling | 04, 17, 20 |
| `docs/product/` | Product vision and requirements | 08 |
| `docs/architecture/` | Architecture overview | 09 |
| `docs/architecture/adr/` | ADRs | 09 |
| `docs/rfc/` | RFCs | 10 |
| `docs/investigations/` | Investigations | 11 |
| `docs/testing/` | Project-wide test strategy and cross-feature evidence | 13 |
| `docs/operations/` and `runbooks/` | Operations and runbooks | 15 |
| `docs/releases/` | Release records | 14 |
| `docs/lessons/` | Lessons learned | 11 |
| `docs/archive/` | Displaced and retired documentation | 28 |
| `docs/templates/` | Non-authoritative templates | 16 |
| `.specify/` | Spec Kit-owned (constitution, templates, scripts, extensions, bug records) | 07 |
| `specs/` | Spec Kit-owned feature artifacts | 07 |

Cross-specification delivery plans, when justified, are stored as `docs/architecture/delivery-plan-<slug>.md` and indexed in `docs/architecture/README.md`; see [chapter 12](12-planning-and-cross-specification-delivery.md). No general `docs/plans/` hierarchy and no `docs/specifications/` store exist.

## 2.5 Native Spec Kit ownership

Spec Kit creates and owns `.specify/`, `specs/`, and integration-specific command or skill directories (for example `.agents/skills/` for Codex or the OpenCode command directory). Nexora does not relocate, rename, or duplicate these. Exact paths are version-sensitive; verify against the pinned release ([chapter 07](07-spec-kit-standard.md)).

## 2.6 Authoritative versus supporting content

- **Authoritative:** governance records, approved product requirements, approved native specifications, accepted ADRs, accepted RFCs (for the decision to proceed only), approved release records, approved runbooks, indexes (for identity and status).
- **Supporting:** templates, drafts, investigations, lessons until incorporated, tool output, AI reviews, temporary handoffs.

## 2.7 Generated versus source content

Source content is edited by people or agents under governance. Generated content (HTML renderings, manifests, coverage reports, tool indexes) is derived and never edited directly. Rules: [chapter 27](27-generated-files-manifests-and-packaging.md).
