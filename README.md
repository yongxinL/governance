# Nexora Governance v1.0.1

**Version:** 1.0.1
**Release tag:** `v1.0.1`
**Status:** Released
**Release date:** 2026-10-21
**Tooling guidance verified:** 2026-10-12

Release 1.0.1 is recorded as released on 2026-10-21. Projects must still verify
the immutable tag and package integrity before adoption.

## Overview

Nexora Governance is the organization-wide documentation, decision, and
delivery governance baseline for Nexora projects. It defines:

- who holds approval authority;
- where authoritative project information lives;
- how changes are specified, decided, implemented, verified, and released;
- how evidence, operational records, and lessons are retained;
- how AI coding agents and supporting tools operate within explicit boundaries.

The package is suitable for both new and existing projects. It provides a
repeatable governance model without making every project copy or independently
maintain the full governance manual.

## Purpose

Nexora Governance exists to make project delivery durable, reviewable, and
recoverable. It replaces conversation-only decisions and ad hoc agent prompts
with committed artifacts, explicit authority, traceable decisions, and honest
validation evidence.

It is intended to ensure that:

- a project can be understood from its repository rather than chat history;
- each information category has one declared source of truth;
- material changes follow a proportionate, reviewable workflow;
- architectural and product decisions remain discoverable;
- AI-generated work remains subordinate to approved requirements and human
  authority;
- tools receive only the access and authority they require;
- governance can evolve through explicit, versioned upgrades.

## Benefits

Adopting Nexora Governance provides:

- **Durable project memory:** decisions, specifications, evidence, and indexes
  are retained in Git.
- **Clear authority:** the Project Owner, accepted decisions, approved
  specifications, and implementation evidence have explicit precedence.
- **Reduced documentation duplication:** GitHub Spec Kit owns its native SDD
  artifacts while Nexora adds governance around them.
- **Safer AI-assisted delivery:** agents operate through repository instructions,
  approval gates, least privilege, and verifiable scope.
- **Consistent project structure:** every adopted project starts from the same
  released scaffold and customizes only project-specific facts.
- **Auditable change:** adoption, exceptions, decisions, releases, and upgrades
  are committed and reviewable.
- **Proportional process:** artifacts are created only when their governance
  purpose applies.
- **Recoverable operations:** source-of-truth ownership, validation evidence,
  and release records reduce reliance on undocumented knowledge.

## Audience

- The Project Owner of each Nexora project. The default operating model is a
  single owner.
- AI coding agents, primarily OpenCode or Codex, operating through each
  project's `AGENTS.md` and approved configuration.
- Future contributors when a project transitions to collaborative governance.
- Reviewers responsible for product, technical, security, operational, or
  release decisions.

## Scope

The package governs:

- product vision and requirements;
- documentation architecture and indexes;
- specifications, plans, tasks, and completion evidence;
- ADRs, RFCs, investigations, and lessons;
- validation and quality gates;
- releases, operations, retention, and migration;
- AI-agent behavior and handoffs;
- developer tools and conditional integrations;
- governance adoption, exceptions, and upgrades.

The package does **not** contain project facts. Each project supplies its own
identity, product definition, requirements, decisions, operational context,
and credentials.

## Key governance principles

1. **The repository is durable memory.** Git history, committed artifacts, and
   indexes are authoritative. Conversation history is not.
2. **One source of truth per information category.** See
   [manual chapter 17](manual/17-indexing-traceability-and-source-of-truth.md).
3. **GitHub Spec Kit owns the Specification-Driven Development workflow and its
   native artifacts.** Nexora adds identifiers, indexes, and approval rules
   around those artifacts. It does not create competing specifications, plans,
   tasks, analyses, or completion records.
4. **Humans retain approval authority.** Material approvals belong to the
   Project Owner. AI output is supporting input only.
5. **Governance is proportional.** Create an artifact only when its governance
   purpose applies.
6. **Tools use least privilege.** Conditional tools start disabled, and
   credentials never enter the repository.
7. **Released governance is immutable.** Projects adopt a semantic version and
   exact release tag, then upgrade through explicit review.
8. **Validation must be honest.** Unperformed checks are reported as not run,
   not represented as successful.

## Central governance model

This package is maintained in a central private repository and released with
semantic versions and immutable tags.

Projects:

- do not copy the governance manual;
- copy the released contents of `project-template/` into the project root;
- record the adopted release in
  `docs/governance/governance-adoption.md`;
- use `CENTRAL-GOVERNANCE-REFERENCE.md` to locate the governing package;
- upgrade only through explicit impact review and approval.

See [manual chapter 02](manual/02-information-architecture.md) and
[manual chapter 04](manual/04-governance-versioning-and-exceptions.md).

## Solo-owner default

The default governance mode is `solo`. One Project Owner performs product,
technical, security, operations, and release review.

The owner records the real approval mode rather than implying independent
review. Supported modes include:

- `owner-self-approval`;
- `enhanced-owner-review`.

See [manual chapter 05](manual/05-lifecycle-ownership-and-approvals.md).

## Prerequisites

Before adopting the package, prepare:

- a Git repository hosted in Nexora Forgejo or an approved equivalent;
- read access to the central governance repository and release tag;
- a named Project Owner;
- one approved primary AI coding-agent harness;
- GitHub Spec Kit (`specify-cli`) installed at a pinned release;
- a clean or explicitly recorded working-tree baseline;
- a dedicated adoption branch for existing projects;
- a credential-management method outside the repository.

The authoritative prerequisite and adoption sequence is maintained in
[instructions/README.md](instructions/README.md).

## Installation and adoption

Nexora Governance is adopted, not installed as an application.

### New project

1. Obtain and verify the released governance package.
2. Read the package README and required manual chapters.
3. Copy `project-template/` into the project root, including hidden files.
4. Replace all customization markers with approved project facts.
5. Configure the selected agent from the provided example configuration.
6. Create product vision and requirements from the templates.
7. Run pinned `specify init` and reconcile the supplied constitution template.
8. Review, validate, and commit the governance, product, and specification
   baselines separately.
9. Execute the first governed change through the native Spec Kit workflow.

See [new-project adoption](instructions/README.md#new-project-adoption).

### Existing project

1. Create an adoption branch and record the current repository state.
2. Add the scaffold without moving, merging, or deleting legacy material.
3. Perform a read-only governance and source-of-truth audit.
4. Resolve authority conflicts before changing legacy documents.
5. Approve a migration map.
6. Migrate in controlled, reviewable batches.
7. Introduce SDD incrementally, beginning with active and high-risk areas.
8. Validate and record the final adoption state.

See [existing-project adoption](instructions/README.md#existing-project-adoption).

## Optional adoption skill

The reusable skill at
`skills/nexora-governance-adopt/SKILL.md` can guide an approved AI agent through
inspection, planning, application, validation, and upgrade.

The skill:

- follows the authoritative instructions and manual;
- distinguishes new-project and existing-project adoption;
- works from an immutable release tag supplied by the Project Owner;
- verifies package integrity before copying the scaffold;
- generates a dry-run plan before modifying a project;
- does not handle credentials;
- does not approve adoption;
- does not commit, push, merge, or install unrelated tools unless explicitly
  authorized.

The skill is an orchestration aid. It does not replace the governance package,
manual, prompts, release manifest, or Project Owner approval.

The skill carries no default governance repository URL. The Project Owner must
supply it. If no governance repository is supplied, the skill stops and reports
that the required input is missing rather than assuming a source.

## Package navigation

| Location | Contents |
|---|---|
| [instructions/README.md](instructions/README.md) | Authoritative package usage and adoption instructions; `README.html` is generated from it |
| [manual/README.md](manual/README.md) | The 30-chapter governance manual |
| [project-template/README.md](project-template/README.md) | Full project scaffold copied into every adopting project |
| [prompts/README.md](prompts/README.md) | Copy-ready agent prompts |
| [skills/](skills/) | Reusable governance skills and supporting resources |
| [VERSION.md](VERSION.md) | Version and compatibility information |
| [CHANGELOG.md](CHANGELOG.md) | Release history and upgrade impact |
| `MANIFEST.json` | SHA-256 and byte size of every package file except itself |

## Adoption entry points

### New project

Read and execute in this order:

1. [Package instructions](instructions/README.md#new-project-adoption)
2. [Chapter 30: Adoption playbook](manual/30-adoption-playbook.md)
3. [Prompt 01: New-project bootstrap](prompts/01-new-project-bootstrap.md)
4. [Prompt 04: Governance adoption review](prompts/04-governance-adoption-review.md)

### Existing project

Read and execute in this order:

1. [Package instructions](instructions/README.md#existing-project-adoption)
2. [Chapter 28: Archive, retention, and migration](manual/28-archive-retention-and-migration.md)
3. [Prompt 02: Existing-project read-only audit](prompts/02-existing-project-read-only-audit.md)
4. [Prompt 03: Governance migration plan](prompts/03-governance-migration-plan.md)
5. [Prompt 04: Governance adoption review](prompts/04-governance-adoption-review.md)

## Daily usage

Use the smallest governed workflow that matches the change:

- Material behavior change: native Spec Kit workflow plus Nexora quality gates.
- Simple single-cause defect: Spec Kit `bug` extension, within limits B1-B9.
- Durable technical decision: ADR.
- Material proposal requiring consultation or staged approval: RFC.
- Material uncertainty: investigation.
- Reusable learning: lesson record where applicable.
- Agent switch: governed handoff using chapter 19 and prompt 21.

See [instructions/README.md#daily-use](instructions/README.md#daily-use).

## Version and release model

Release `1.0.1` is recorded as Released on 2026-10-21 for tag `v1.0.1`.

Version `1.0.0` was declared Released on 2026-10-12 at source baseline
`d00dcab5f70c083a37d612e48eacb67e38aa272e`. No `v1.0.0` tag was found in the
local repository or on `origin`; see
[VERSION.md](VERSION.md#verified-100-baseline).

Corrections in `1.0.1` require no migration. A project adopted on `1.0.0` keeps
its obligations unchanged.

Patch, minor, and major releases follow
[manual chapter 04](manual/04-governance-versioning-and-exceptions.md).
Projects remain on their recorded release until an explicit upgrade is reviewed,
approved, validated, and committed.

## Package integrity and validation

This release was validated against the eight release gates in
[manual chapter 26](manual/26-validation-and-quality-gates.md) and
[manual chapter 27](manual/27-generated-files-manifests-and-packaging.md),
including validation after clean ZIP extraction.

Before adoption:

1. verify the immutable tag;
2. verify the published archive checksum when using a release archive;
3. verify package contents using `MANIFEST.json`;
4. confirm the instructions, templates, prompts, and manual correspond to the
   same release;
5. stop if integrity validation fails.

`MANIFEST.json` contains the SHA-256 digest and byte size of every package file
except itself. It is generated last.

## Generated artifacts

- `instructions/README.md` is authoritative.
- `instructions/README.html` is generated from the Markdown source and must not
  be edited directly.
- `MANIFEST.json` is generated after all package content is finalized.
- Markdown source files are authoritative over generated HTML.

## Security

- Keep credentials, tokens, private keys, and cookies outside Git.
- Use read-only access to retrieve governance releases.
- Do not embed credentials in repository URLs.
- Keep conditional tools disabled until they are explicitly approved.
- Review all generated diffs before commit.
- Do not allow an AI agent to approve its own work.
- Do not disable TLS verification or bypass package-integrity failures.

## Support and change proposals

Propose governance changes through the process defined by the manual. A change
to this package must preserve source-of-truth ownership, update affected
cross-references, regenerate derivative artifacts, regenerate `MANIFEST.json`,
and pass all release gates before a new immutable tag is published.

## Release record for v1.0.1

These corrections are additive and corrective. They must not be published under
the `v1.0.0` identity, and no existing tag is moved or rewritten.

Release `v1.0.1` is finalized only after all source, generated-file, manifest,
archive, clean-extraction, and eight-gate validation checks pass. External
publication, upload, deployment, and merge remain separate Project Owner
decisions.
