# Nexora Governance v1.0.1: Instructions

**Version:** 1.0.1
**Release tag:** `v1.0.1`
**Status:** Released
**Release date:** 2026-10-21

This file is the authoritative adoption source for released version 1.0.1.

> `instructions/README.html` is generated from this file and must not be edited
> directly. If the files differ, this Markdown source is authoritative and the
> HTML must be regenerated.

## Purpose

These instructions define how to adopt and use the Nexora Governance package.
Detailed policy belongs to the linked manual chapters; this file sequences the
required work and identifies the authoritative entry points.

Do not replace these instructions with an AI-generated summary. Summaries and
skills may assist execution but remain subordinate to this file and the manual.

## Authority boundaries

- The central manual is authoritative for organization-wide governance policy.
- Project governance records specialize the adopted release. They must not
  silently weaken, override, or contradict it.
- Prompts, project templates, tools, and skills are supporting mechanisms. None
  of them is an authority source.
- The Project Owner retains material approval authority. No agent, prompt,
  template, or skill may approve on the owner's behalf.
- Native GitHub Spec Kit owns `.specify/`, `specs/`, specifications, plans,
  tasks, analyses, and convergence artifacts. These instructions must not create
  competing artifacts or a competing workflow owner.
- Where this file and the manual appear to differ, the manual governs and this
  discrepancy is reported as a validation finding.

## What to read first

Read in this order:

1. [Package README](../README.md): purpose, principles, benefits, navigation,
   version, and package-integrity model.
2. [Chapter 01: Governance policy](../manual/01-governance-policy.md): authority
   and non-exception controls.
3. [Chapter 02: Information architecture](../manual/02-information-architecture.md):
   canonical locations and project structure.
4. [Chapter 07: Spec Kit standard](../manual/07-spec-kit-standard.md): SDD
   ownership and compatible integration.
5. [Chapter 17: Indexing, traceability, and source of truth](../manual/17-indexing-traceability-and-source-of-truth.md):
   authority per information category.
6. [Chapter 30: Adoption playbook](../manual/30-adoption-playbook.md): complete
   adoption procedure.

Existing projects must also read
[chapter 28](../manual/28-archive-retention-and-migration.md) before moving,
merging, archiving, or deleting legacy material.

## Prerequisites

Before adoption, confirm:

- A Git repository hosted under the Nexora Forgejo organization or an approved
  equivalent exists.
- A named Project Owner is identified.
- Read access to the central governance repository and immutable release tag is
  configured outside the target repository.
- The package release or archive has passed integrity verification.
- The target repository state is clean, or existing changes are recorded and
  protected.
- One primary coding-agent harness is selected: OpenCode v2 configuration or
  Codex, unless a governed exception approves another harness.
- GitHub Spec Kit (`specify-cli`) is installed at a pinned compatible release.
- Credentials and secrets are managed outside Git.

Do not continue to application if required project identity, release,
compatibility, or integrity information is missing.

## Verify the governance package

Before copying any project files:

1. Check out or extract the exact approved release. The governance repository
   location is a required configuration input, represented here as
   `<GOVERNANCE_REPOSITORY_URL>`. This package deliberately ships no default
   governance repository URL; the Project Owner supplies it.
2. Verify the Git tag or published archive checksum.
3. Verify each packaged file against `MANIFEST.json`.
4. Confirm `VERSION.md`, `CHANGELOG.md`, this file, the manual, prompts, and
   project template belong to the same release.
5. Stop if a digest, byte size, release identifier, or required file does not
   match.

Release history for this package:

- The `1.0.0` release was declared Released on 2026-10-12 at the verified source
  baseline commit `d00dcab5f70c083a37d612e48eacb67e38aa272e`.
- No local or origin `v1.0.0` tag was found. The missing tag does not invalidate
  the release declaration, and this package does not create a retrospective tag.

A project that already adopted `1.0.0` requires no migration for `1.0.1`.

`MANIFEST.json` covers every package file except itself and is generated last.
See [chapter 27](../manual/27-generated-files-manifests-and-packaging.md).

## Package adoption requirements

For both adoption paths:

- verify the released package before using any of its contents;
- copy the complete released `project-template/` contents, including approved
  hidden files such as `.codex/`;
- do not copy the central manual into each project;
- record the adopted release, tag, and date in
  `docs/governance/governance-adoption.md`;
- reference the governing central package through
  `CENTRAL-GOVERNANCE-REFERENCE.md` rather than copying central policy;
- treat existing-project adoption as inspect, plan, approve, then apply;
- do not delete or overwrite existing authoritative content before migration
  authority is established.

## New-project adoption

This path applies when the target repository does not yet contain an established
project documentation and delivery system that requires migration.

| Stage | Action | Owning chapter |
|---|---|---|
| 1 | Verify the governance release and package integrity. | 27, 30 |
| 2 | Copy the contents of `project-template/` into the target project root, including hidden files such as `.codex/`. Example: `cp -a project-template/. <project-root>/`. | 30 |
| 3 | Replace every customization marker in governance files, `AGENTS.md`, and `CENTRAL-GOVERNANCE-REFERENCE.md`. Do not invent missing values. | 02, 30 |
| 4 | Choose the primary agent. Create live configuration from `opencode.json.example` or `.codex/config.toml.example`. Keep conditional tools disabled and credentials outside Git. | 20-25 |
| 5 | Create `docs/product/vision.md` and `docs/product/requirements.md` from the supplied templates. | 08 |
| 6 | Run pinned `specify init --here --integration <key>` and let Spec Kit create its native `.specify/` and `specs/` artifacts. | 07 |
| 7 | Reconcile `SPEC-KIT-CONSTITUTION-TEMPLATE.md` into the native Spec Kit constitution, review and approve it, then remove the temporary template. | 07 |
| 8 | Create `specs/README.md` only after confirming compatibility with the installed Spec Kit version. | 17 |
| 9 | Run validation and review the complete Git diff. | 26, 27 |
| 10 | Commit separate, reviewable baselines for governance, product definition, and the approved constitution. | 05 |
| 11 | Run prompt 04 and record readiness for Level 1: Controlled. | 29, 30 |
| 12 | Execute the first governed change through the native Spec Kit workflow. | 06, 07 |

Use:

- [Prompt 01: New-project bootstrap](../prompts/01-new-project-bootstrap.md)
  for scaffold and agent configuration;
- [Prompt 04: Governance adoption review](../prompts/04-governance-adoption-review.md)
  for adoption readiness.

### New-project restrictions

During bootstrap:

- do not copy the central manual into the target project;
- do not omit hidden template files;
- do not create competing specification, planning, task, analysis, or
  completion artifacts;
- do not commit example files as live configuration without customization;
- do not enable conditional tools by default;
- do not allow the AI agent to approve the adoption;
- do not claim validation that was not performed.

## Existing-project adoption

This path applies when the target repository contains established documents,
source-of-truth locations, agent instructions, or delivery artifacts that may
conflict with the Nexora scaffold.

| Stage | Action | Owning chapter |
|---|---|---|
| 1 | Create an adoption branch and record the current commit, branch, remotes, and working-tree state. | 28 |
| 2 | Verify the governance release and package integrity. | 27, 30 |
| 3 | Add the scaffold without moving, merging, rewriting, archiving, or deleting legacy documents. | 28 |
| 4 | Run the read-only audit using prompt 02. | 28, 29 |
| 5 | Inventory legacy and new source-of-truth claims. Resolve authority conflicts before content movement. | 17, 28 |
| 6 | Prepare and approve a migration map using prompt 03. Classify work as safe automatic, careful consolidation, or owner decision. | 28 |
| 7 | Apply migrations in small, reviewable batches with validation and rollback boundaries. | 26, 28 |
| 8 | Introduce SDD incrementally, beginning with active and high-risk areas. Do not recreate historical work merely to populate templates. | 06, 07 |
| 9 | Reconcile agent instructions and tooling without silently overwriting established constraints. | 19-25 |
| 10 | Complete adoption, run prompt 04, and record the actual adoption state. | 29, 30 |

Use:

- [Prompt 02: Existing-project read-only audit](../prompts/02-existing-project-read-only-audit.md);
- [Prompt 03: Governance migration plan](../prompts/03-governance-migration-plan.md);
- [Prompt 04: Governance adoption review](../prompts/04-governance-adoption-review.md).

### Existing-project restrictions

Until the migration map is approved:

- do not move or rename legacy documents;
- do not merge duplicate-looking files;
- do not rewrite or archive existing decisions;
- do not delete apparently obsolete content;
- do not replace existing `AGENTS.md`, agent configuration, ADRs, or active
  specifications silently;
- do not treat folder similarity as proof of equivalent authority;
- do not initialize a competing SDD structure.

## Agent-assisted adoption skill

The package may include the reusable skill:

```text
skills/nexora-governance-adopt/SKILL.md
```

The skill can assist with:

- package and project inspection;
- new-versus-existing project classification;
- dry-run adoption plans;
- scaffold-copy planning;
- customization-marker inventory;
- existing-project conflict and migration analysis;
- validation and upgrade reports;
- upgrade-impact assessment.

The skill must:

- read this file before planning adoption;
- read the required manual chapters and prompts for the selected path;
- verify the immutable release and `MANIFEST.json`;
- use the full `project-template/` as the scaffold source;
- preserve hidden files;
- stop for owner decisions and approval;
- keep credentials outside its inputs and outputs;
- avoid commits, pushes, merges, and tool installation unless explicitly
  authorized.

The skill is optional and non-authoritative. It does not replace:

- `README.md`;
- this file;
- `manual/`;
- `prompts/`;
- `project-template/`;
- `MANIFEST.json`;
- native GitHub Spec Kit workflows;
- Project Owner approval.

The skill must not commit, push, merge, tag, publish, deploy, install or enable
tools, or approve anything without explicit authorization. When the governance
repository has not been supplied, it must stop and report the missing required
input rather than assuming a default source.

## Daily use

Select the smallest applicable governed workflow:

- **Material behavior change:** native Spec Kit workflow with Nexora quality
  gates from [chapter 26](../manual/26-validation-and-quality-gates.md).
- **Simple single-cause defect:** Spec Kit `bug` extension within limits B1-B9
  from [chapter 07](../manual/07-spec-kit-standard.md).
- **Durable technical decision:** ADR under
  [chapter 09](../manual/09-adr-standard.md).
- **Material proposal:** RFC under
  [chapter 10](../manual/10-rfc-standard.md).
- **Material uncertainty:** investigation under
  [chapter 11](../manual/11-investigations-and-lessons.md).
- **Agent switch:** follow
  [chapter 19](../manual/19-agent-switching-and-handoffs.md) and
  [prompt 21](../prompts/21-agent-switch-handoff.md).

Do not create an ADR, RFC, investigation, or other artifact solely to make a
project appear complete. Apply proportionality.

## Installing and configuring project tools

### GitHub Spec Kit

Spec Kit installation and initialization are a separate governed stage. They are
not a side effect of copying the scaffold and must not run automatically during
inspection or planning.

- Install `specify-cli` at a pinned compatible release.
- Run initialization only as an explicit, reviewable, separately approved stage.
- Record the adopted version in project tooling records.
- Run `specify init` only after the governance and product baseline is ready for
  reconciliation.
- Preserve Spec Kit ownership of `.specify/`, `specs/`, and native workflow
  artifacts.
- Do not relocate or duplicate its specifications, plans, tasks, analyses, or
  completion records.

### Product definition

- Create `docs/product/vision.md` and `docs/product/requirements.md` from the
  supplied templates before the specification baseline is treated as ready.
- Product vision and product requirements are distinct authoritative locations.
  Do not merge them or duplicate either into the specification tree.
- Do not invent product facts, dates, approvals, or evidence. Unresolved values
  remain explicit markers until the Project Owner supplies them.

### AI coding agent

- Choose OpenCode or Codex as the primary harness unless a governed exception
  permits another.
- Generate live configuration from the corresponding example.
- Keep `AGENTS.md` as the project instruction authority.
- Keep conditional tools disabled until approved.
- Pin tool and model configuration where the project requires reproducibility.

### Credentials

- Do not store credentials in the repository, prompts, examples, logs, or
  generated adoption reports.
- Use SSH agents, credential helpers, environment injection, or an approved
  secret manager.
- Do not embed credentials in Git URLs.

## Upgrading governance

1. Read the central `CHANGELOG.md` and `VERSION.md`.
2. Resolve the current and proposed release tags and commits.
3. Review all required migrations.
4. Compare project-template, instruction, prompt, schema, and validation
   changes.
5. Assess existing project exceptions and tool compatibility.
6. Prepare an impact and migration plan.
7. Apply the upgrade on a dedicated branch.
8. Update `docs/governance/governance-adoption.md` only after review.
9. Validate the project and record approval honestly.
10. Commit the upgrade as a governed change.

Major releases require an adoption review using
[prompt 04](../prompts/04-governance-adoption-review.md). See
[chapter 04](../manual/04-governance-versioning-and-exceptions.md).

## Validating this package

Package integrity is verified with:

- immutable release tag;
- published archive SHA-256, where applicable;
- `MANIFEST.json` SHA-256 and byte size for every package file except itself;
- release-gate validation;
- clean archive extraction and validation.

See [chapter 27](../manual/27-generated-files-manifests-and-packaging.md).

Do not adopt or distribute a package when integrity validation fails.

## Generated files

- `README.html` is derived from this file.
- If the HTML and Markdown differ, this file is authoritative.
- Regenerate generated HTML after changing this source.
- Regenerate `MANIFEST.json` after all source and generated artifacts are
  finalized.
- Never manually edit `MANIFEST.json` as if it were an ordinary source file.

## Completion criteria

Adoption is not complete until:

- the correct adoption path was followed;
- the immutable release and package integrity were verified;
- project-template customization is complete;
- source-of-truth conflicts are resolved or explicitly blocked;
- agent and tooling configurations follow least privilege;
- Spec Kit ownership is preserved;
- required validation has passed;
- unperformed validation is disclosed;
- Project Owner approval is recorded with the actual approval mode;
- the adoption state and release reference are committed.
