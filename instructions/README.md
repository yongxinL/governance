# Nexora Governance v1.0 - Instructions

**Version:** 1.0.0 · **Tag:** `v1.0.0` · **Status:** Authoritative source. `README.html` in this directory is generated from this file and must not be edited directly.

These instructions explain how to use the package. Detailed rules live in the [manual](../manual/README.md); this file sequences them and links to the owning chapters.

## 1. What to read first

1. [Package README](../README.md) - principles and navigation.
2. [Chapter 01 - Governance policy](../manual/01-governance-policy.md) - authority and non-exception controls.
3. [Chapter 02 - Information architecture](../manual/02-information-architecture.md) - where things live.
4. [Chapter 07 - Spec Kit standard](../manual/07-spec-kit-standard.md) - workflow ownership.
5. [Chapter 30 - Adoption playbook](../manual/30-adoption-playbook.md) - full adoption procedure.

## 2. Prerequisites

- A Git repository hosted under the Nexora Forgejo organization or equivalent.
- An access path to the central governance repository at tag `v1.0.0`.
- One primary agent: OpenCode (v2 configuration format) or Codex.
- GitHub Spec Kit (`specify-cli`) installed at a pinned release (see chapter 07).
- A named Project Owner.

## New-project adoption

| Stage | Action | Owning chapter |
|---|---|---|
| 1 | Copy the contents of `project-template/` into the project root, **including hidden files** (`.codex/`). Example: `cp -a project-template/. <project-root>/` | 30 |
| 2 | Replace customization markers in governance files, `AGENTS.md`, and `CENTRAL-GOVERNANCE-REFERENCE.md`. Do not invent missing values. | 30 |
| 3 | Choose the primary agent; create live configuration from `opencode.json.example` or `.codex/config.toml.example`; keep conditional tools disabled; keep credentials out of Git. | 20, 21-25 |
| 4 | Create `docs/product/vision.md` and `docs/product/requirements.md` from the product templates. | 08 |
| 5 | Run the pinned `specify init --here --integration <key>`; let Spec Kit create `.specify/` and `specs/`. | 07 |
| 6 | Reconcile `SPEC-KIT-CONSTITUTION-TEMPLATE.md` into the native constitution, approve it, then remove the template. | 07 |
| 7 | Create `specs/README.md` only after confirming compatibility with the installed Spec Kit version. | 17 |
| 8 | Commit baselines (example messages: `docs: establish Nexora project governance scaffold`, `docs(product): define product vision and requirements`, `docs(spec): approve project constitution`). | 05 |
| 9 | Execute the first governed change through the native workflow. | 06, 07 |

Use prompt [01](../prompts/01-new-project-bootstrap.md) for stages 1-3 and prompt [04](../prompts/04-governance-adoption-review.md) to review readiness for Level 1: Controlled.

## Existing-project adoption

| Stage | Action | Owning chapter |
|---|---|---|
| 1 | Create an adoption branch; record the current commit and working-tree state. | 28 |
| 2 | Add the scaffold without moving or merging legacy documents. | 28 |
| 3 | Run the read-only audit (prompt [02](../prompts/02-existing-project-read-only-audit.md)). | 28, 29 |
| 4 | Resolve source-of-truth conflicts before any move, merge, rewrite, archive, or deletion. | 17, 28 |
| 5 | Approve a migration map (prompt [03](../prompts/03-governance-migration-plan.md)): safe automatic, careful consolidation, owner decision. | 28 |
| 6 | Migrate in controlled batches. | 28 |
| 7 | Introduce SDD incrementally, starting with active and high-risk areas. | 06 |
| 8 | Complete adoption and record the adoption state. | 29, 30 |

## 3. Daily use

- Material behaviour change: native Spec Kit workflow plus Nexora gates ([chapter 26](../manual/26-validation-and-quality-gates.md)).
- Simple single-cause defects: Spec Kit `bug` extension within limits B1-B9 ([chapter 07](../manual/07-spec-kit-standard.md)).
- Durable technical decisions: ADR ([chapter 09](../manual/09-adr-standard.md)).
- Material proposals: RFC ([chapter 10](../manual/10-rfc-standard.md)).
- Material uncertainty: investigation ([chapter 11](../manual/11-investigations-and-lessons.md)).
- Switching agents: [chapter 19](../manual/19-agent-switching-and-handoffs.md) and prompt [21](../prompts/21-agent-switch-handoff.md).

## 4. Upgrading governance

Read the central `CHANGELOG.md`, review impact, update `docs/governance/governance-adoption.md` to the new version and tag, and commit the adoption as a governed change. Major releases require an adoption review using prompt [04](../prompts/04-governance-adoption-review.md). See [chapter 04](../manual/04-governance-versioning-and-exceptions.md).

## 5. Validating this package

Package integrity is verified with `MANIFEST.json` (SHA-256 per file) and the published ZIP SHA-256. See [chapter 27](../manual/27-generated-files-manifests-and-packaging.md).

## 6. Generated files

`README.html` is a derivative of this file. If they differ, this Markdown file is authoritative and the HTML must be regenerated.
