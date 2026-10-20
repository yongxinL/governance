---
name: nexora-governance-adopt
description: >
  Adopt, validate, audit, or upgrade a pinned Nexora Governance release in a
  project using the versioned-reference model. Use when initializing project
  governance, repairing an incomplete adoption, checking compliance, or
  upgrading an existing governance baseline.
argument-hint: >
  [inspect|plan|apply|validate|upgrade] [--version <tag>]
  [--project-code <code>] [--project-name <name>]
disable-model-invocation: true
---

# Nexora Governance Adoption

Adopt a released Nexora Governance baseline into the current project using the
versioned-reference adoption model.

The authoritative governance source is a repository supplied by the Project
Owner as an explicit input, recorded as `<GOVERNANCE_REPOSITORY_URL>`.

This skill ships **no default governance repository**. That value is
deployment-specific and must never be baked into reusable content. If no
repository has been supplied, stop and report that the required input is
missing. Do not fall back to an assumed, remembered, or previously used source.

This skill must not reconstruct governance from model memory. It must inspect
and follow the authoritative package materials contained in the requested
pinned governance release.

The authoritative adoption sequence begins with:

- `README.md` for package purpose, principles, navigation, and release status;
- `instructions/README.md` for authoritative usage and adoption instructions;
- `manual/01-governance-policy.md` for authority and non-exception controls;
- `manual/02-information-architecture.md` for canonical locations;
- `manual/07-spec-kit-standard.md` for SDD ownership;
- `manual/17-indexing-traceability-and-source-of-truth.md` for authority per
  information category;
- `manual/30-adoption-playbook.md` for the complete adoption procedure.

For existing projects, also read
`manual/28-archive-retention-and-migration.md` before proposing any move,
merge, rewrite, archive, or deletion.

The skill is an orchestration aid. It does not replace the package README,
authoritative instructions, manual, prompts, `MANIFEST.json`, or Project Owner
approval.

## Invocation policy

This skill is **optional** and **non-authoritative**. It orchestrates an approved
governance workflow; it never defines, replaces, weakens, or supersedes
governance. It does not replace `README.md`, `instructions/README.md`, `manual/`,
`prompts/`, `project-template/`, `MANIFEST.json`, native GitHub Spec Kit
workflows, or Project Owner approval. Where this skill and any of those disagree,
they govern and the difference is reported.

This skill must be explicitly invoked by the user.

Do not adopt, upgrade, repair, or modify project governance merely because a
repository does not contain governance files.

Default operating mode: `plan`

The supported modes are:

- `inspect`: inspect the project and governance source without producing an
  adoption plan or modifying project files;
- `plan`: inspect both sources and produce a dry-run adoption plan without
  modifying project files;
- `apply`: apply a previously reviewed plan or create a plan and stop for
  approval before applying it;
- `validate`: validate an existing adoption without changing it;
- `upgrade`: compare the adopted baseline with a newer pinned release and
  produce an impact and migration plan.

## Required inputs

Obtain the following values from explicit arguments, approved project metadata,
or the user:

- project name;
- project short name;
- project code;
- project repository identifier;
- project owner;
- governance release or tag;
- governance source mode;
- primary AI-agent harness;
- requested operating mode.

Valid governance source modes are:

- `local`: use a pre-authenticated local Git checkout;
- `git`: access the remote repository using the user's existing Git
  authentication.

Do not invent:

- a governance version;
- a project code;
- a project owner;
- approval evidence;
- an approval date;
- a governance release commit;
- an adoption baseline commit;
- an exception or waiver.

If required information cannot be resolved safely, stop and report the missing
input.

## Authority

The checked-out, pinned Nexora Governance release is authoritative for:

- the governance adoption process;
- required project-local adoption artifacts;
- managed templates;
- schemas and validation rules;
- authority precedence;
- exception handling;
- tooling-adoption requirements;
- governance-upgrade requirements.

This `SKILL.md` orchestrates the process. It does not replace or override the
pinned governance release.

When instructions conflict, apply this precedence:

1. applicable law, security obligations, and organizational controls;
2. the pinned Nexora Governance release;
3. accepted project governance and approved exceptions;
4. accepted RFCs and ADRs;
5. approved product requirements and specifications;
6. approved implementation plans and tasks;
7. repository validation, tests, and operational evidence;
8. project-level agent instructions;
9. this skill;
10. the current user prompt.

Stop and report any unresolved conflict between higher-authority artifacts.

## Private repository authentication

The Nexora Governance repository is private. Authentication must be configured
by the user outside this skill through an approved Git authentication
mechanism.

Accepted mechanisms include:

- an existing SSH agent and approved SSH key;
- an existing operating-system-backed Git credential helper;
- a pre-authenticated local checkout;
- a CI credential made available directly to Git without exposing it to the
  model.

The preferred initial method is a pre-authenticated, pinned local checkout.

The skill must not:

- ask the user to paste a password, personal access token, private key, session
  cookie, or other secret into chat;
- create or rotate a Forgejo personal access token;
- read SSH private-key files;
- read Git credential stores;
- store credentials in the target project;
- store credentials in the governance checkout;
- add credentials to a Git URL;
- print authentication headers or credential values;
- expose credentials in logs, reports, diffs, or error messages;
- modify the user's Git credential configuration;
- disable TLS certificate verification;
- downgrade to an insecure transport;
- copy credential-bearing Git configuration into project files.

Reject repository URLs containing embedded user information or credentials,
including URLs shaped like:

`https://username:secret@example.invalid/repository.git`

If remote authentication fails, report only:

- that repository access failed;
- the sanitized repository URL;
- whether HTTPS or SSH was attempted;
- the sanitized Git error;
- that authentication must be configured outside the skill.

Never request the credential value.

## Release and version rules

The governance reference must be immutable and reproducible.

Require an explicit release tag or immutable commit approved by the user.

Reject these references in `apply` and `upgrade` modes:

- `main`;
- `master`;
- `HEAD`;
- `latest`;
- an unresolved symbolic reference;
- an uncommitted local worktree;
- an untagged moving branch unless a development-only exception is explicitly
  approved.

Resolve and record both:

- the requested governance tag;
- the exact governance release commit SHA.

Do not confuse the governance release commit with the target project's later
adoption-baseline commit.

An upgrade must compare the currently adopted version and commit with the
requested version and commit before proposing changes.

## Package structure and integrity

Before producing an adoption plan, inspect and validate the selected release.

Required package locations include:

- `README.md`;
- `instructions/README.md`;
- `manual/README.md` and required manual chapters;
- `project-template/README.md` and the complete `project-template/` scaffold;
- `prompts/README.md` and adoption prompts;
- `VERSION.md`;
- `CHANGELOG.md`;
- `MANIFEST.json`.

The package may also contain reusable skills under `skills/`.

Verify that:

1. the selected tag is immutable and resolves to an exact commit;
2. `VERSION.md`, `CHANGELOG.md`, package metadata, and instructions identify a
   compatible release;
3. every package file covered by `MANIFEST.json` has the recorded SHA-256 and
   byte size;
4. `MANIFEST.json` excludes itself as defined by the package release model;
5. generated files are treated as derivatives of their declared Markdown
   sources;
6. integrity verification completes before scaffold files are copied.

If a digest, byte size, version, tag, or required package file does not match,
stop with status `BLOCKED`. Do not bypass or repair package integrity inside the
target project.

`instructions/README.md` is authoritative over its generated
`instructions/README.html`. Never edit or use the generated HTML as the source
for adoption changes.

## Adoption-path classification

Classify the target before planning changes.

Use `NEW_PROJECT` when the repository does not have an established project
documentation and delivery system requiring migration.

Use `EXISTING_PROJECT` when the repository already contains project facts,
legacy documentation, source-of-truth claims, accepted decisions, agent
instructions, specifications, plans, or delivery artifacts that may overlap or
conflict with the Nexora scaffold.

Use `AMBIGUOUS` when the evidence does not reliably distinguish the two. Stop and
request Project Owner classification. Do not silently assume the lower-risk
path: applying scaffold content over established artifacts can destroy real
authority, while classifying a genuinely new repository as existing only costs an
extra read-only audit. Never resolve `AMBIGUOUS` by guessing.

Record both:

- repository adoption condition, such as `new-adoption`,
  `existing-compliant-adoption`, `incomplete-adoption`, `upgrade-required`,
  `conflict`, or `not-applicable`;
- adoption path: `NEW_PROJECT`, `EXISTING_PROJECT`, or `AMBIGUOUS`.

## General safety requirements

Before modifying the target project:

1. Confirm the current directory is the intended project root.
2. Confirm it is a Git repository.
3. Record the current branch and current commit.
4. Inspect the worktree for uncommitted changes.
5. Refuse `apply` on `main`, `master`, or another protected default branch.
6. Require a dedicated governance branch for `apply` or `upgrade`.
7. Inspect the existing project governance and agent instructions.
8. Inspect the pinned governance release's adoption instructions.
9. Produce a dry-run plan before changing project files.
10. Identify all planned file creations, modifications, and preserved files.
11. Stop if blocking conflicts or unresolved owner decisions remain.

Do not run unreviewed hooks or arbitrary executable content merely because it
exists in the target project or governance repository.

Do not commit, push, open a pull request, merge, tag, or approve governance
unless the user explicitly authorizes that separate action.

### Git safety for any write-capable step

Before and during any change:

1. `git branch --show-current` and `git status --short` to record the state.
2. Confirm every path intended to change is inside the reviewed write scope.
3. `git diff --check` and resolve whitespace and conflict-marker defects.
4. Read the complete diff, not only the expected files.
5. Report validation performed and validation not performed.
6. Report the working-tree state before declaring readiness.

Before an authorized commit:

1. Stage explicit paths or a reviewed patch. Never `git add -A` without first
   reviewing the exact resulting staged list.
2. `git diff --cached --name-only` and confirm only intended paths are staged.
3. `git diff --cached --check`.
4. Read the complete staged diff.
5. Run stage-specific validation and scan staged content for secrets.
6. Report the working-tree state.

Never discard uncommitted work that is not this skill's to discard. Recovery must
restore or revert specific paths, never destructive cleanup for convenience.

### Result vocabulary and severity

Record every check with exactly one canonical outcome: `PASS`, `FAIL`, `BLOCKED`,
`NOT_RUN`, or `NOT_APPLICABLE`. A check that was not run is `NOT_RUN` and is
never `PASS`; an unavailable prerequisite is `BLOCKED`, never silently passed.

Record findings as `BLOCKING`, `MAJOR`, or `MINOR`. Never use percentage scoring
that could hide a failed mandatory control.

Use `Pending` or an unresolved marker for anything awaiting a real Project Owner
decision. Never pre-populate an approver, approval mode, approval date, or
completed validation evidence.

## Governance source handling

### Local source mode

Prefer a trusted local checkout such as:

`~/.local/share/nexora/governance`

Verify:

- the path exists;
- it is a Git repository;
- the worktree is clean;
- its configured remote matches the approved governance repository;
- the requested release exists locally;
- the requested release resolves to an exact commit;
- the checked-out files correspond to that release.

Do not fetch or access the network in local mode unless the user explicitly
requests an update.

Do not modify the local governance checkout.

### Remote Git source mode

Use only the clean approved repository URL supplied by the Project Owner as
`<GOVERNANCE_REPOSITORY_URL>`. Never embed credentials in it.

An approved SSH equivalent may be used if supplied or already configured by
the user.

If no repository URL has been supplied, remote mode is unavailable. Stop and
report the missing input rather than substituting any default.

Before cloning, use a non-destructive access check such as:

`git ls-remote <sanitized-repository-url> <requested-tag>`

Allow Git to use the user's existing authentication. Do not intercept or
inspect the credential.

Clone into an operating-system temporary directory outside the target project.
Use a detached checkout of the requested release. Remove the temporary checkout
when the operation completes, unless evidence-retention rules require a
sanitized manifest or checksum record.

Never add the governance repository as a Git submodule or permanent project
remote unless an accepted decision explicitly requires it.

## Adoption model

Use the versioned-reference model.

The complete organizational governance package remains authoritative in its
central private repository. Do not copy the central manual into the target
project.

For every adopting project, use the complete released `project-template/` as
the scaffold source. Copy its **contents** into the target project root,
including hidden files such as `.codex/`. Do not select an improvised subset of
the scaffold.

For a new project, the plan must include:

1. copy `project-template/.` to the target project root while preserving hidden
   files and file modes;
2. inventory and replace customization markers in governed files,
   `AGENTS.md`, and `CENTRAL-GOVERNANCE-REFERENCE.md`;
3. obtain missing values from approved project metadata or the Project Owner;
4. create live OpenCode or Codex configuration from the corresponding example;
5. keep conditional tools disabled and credentials outside Git;
6. create product vision and requirements from the supplied templates;
7. run pinned `specify init --here --integration <key>` separately and allow
   Spec Kit to create `.specify/` and `specs/`;
8. reconcile `SPEC-KIT-CONSTITUTION-TEMPLATE.md` into the native constitution,
   obtain Project Owner approval, and remove the temporary template;
9. create `specs/README.md` only after compatibility with the installed Spec
   Kit version is confirmed;
10. validate and create separate reviewable governance, product, and
    constitution baselines.

For an existing project, first add the scaffold without moving, merging,
rewriting, archiving, or deleting legacy content. Then:

1. run the read-only audit using `prompts/02-existing-project-read-only-audit.md`;
2. inventory all legacy and scaffold source-of-truth claims;
3. stop on authority conflicts;
4. prepare a migration map using
   `prompts/03-governance-migration-plan.md`;
5. classify migrations as safe automatic, careful consolidation, or owner
   decision;
6. require Project Owner approval before migration;
7. migrate in controlled batches;
8. introduce SDD incrementally, beginning with active and high-risk areas;
9. complete readiness review with
   `prompts/04-governance-adoption-review.md`.

The project records the adopted release in
`docs/governance/governance-adoption.md` and retains the central relationship
through `CENTRAL-GOVERNANCE-REFERENCE.md` as defined by the scaffold.

## Inspection phase

Inspect the target project for:

- project identity and repository metadata;
- Git branch, commit, remotes, and worktree status;
- existing `AGENTS.md`;
- existing `CLAUDE.md` or other harness-specific instruction files;
- `docs/governance/` or equivalent governance locations;
- an existing governance adoption manifest;
- `.specify/` and `specs/`;
- existing ADR and RFC structures;
- existing product and architecture documentation;
- competing specification or planning locations;
- accepted exceptions;
- existing tool-adoption records;
- possible conflicts with managed files;
- possible credentials or secret values in proposed changes.

Inspect the pinned governance release for:

- its version and release commit;
- adoption instructions;
- adoption manifest or schema;
- project-overlay templates;
- validators;
- migration instructions;
- compatibility requirements;
- agent integration guidance;
- required approval gates.

Classify the project as one of:

- `new-adoption`;
- `existing-compliant-adoption`;
- `incomplete-adoption`;
- `upgrade-required`;
- `conflict`;
- `not-applicable`.

## Planning phase

Generate both a human-readable and machine-readable adoption plan when the
pinned governance release supports them.

The plan must identify:

- target project identity;
- governance source type;
- sanitized governance repository URL or trusted local path;
- requested release;
- resolved governance release commit;
- detected current adoption, if any;
- adoption classification;
- files to create;
- files to update;
- files to preserve unchanged;
- files that require manual reconciliation;
- detected conflicts;
- missing inputs;
- required owner decisions;
- validation commands;
- approval gates;
- rollback steps;
- whether Spec Kit is already present;
- whether agent-specific files require reconciliation;
- whether the plan is safe to apply.

Planning mode must not modify authoritative project files.

Store temporary plans outside authoritative project directories unless the
pinned governance release defines a governed plan/evidence location.

Assign the plan a checksum or immutable identifier when supported. `apply`
should use the reviewed plan rather than silently regenerating a meaningfully
different one.

## Approval gate

Stop after planning unless:

- the user explicitly requested `apply`; and
- the plan contains no unresolved blocking conflicts; and
- any approval required by the pinned governance release has been provided.

Even in `apply` mode, if the plan has not previously been reviewed, present the
plan and stop before making changes unless the user explicitly authorized
plan-and-apply in one operation and the governance release permits it.

The AI agent may not approve:

- governance adoption;
- governance upgrades;
- project exceptions;
- ADRs or RFCs;
- its own generated work.

## Apply phase

When explicitly authorized:

1. Confirm the reviewed plan identifier or checksum.
2. Confirm a dedicated governance branch is active.
3. Apply only the files and changes defined by the reviewed plan.
4. Use the templates and generators from the pinned governance release.
5. Preserve existing files unless an approved migration rule allows an update.
6. Never silently overwrite `AGENTS.md`, `CLAUDE.md`, accepted ADRs, active
   specifications, or approved exceptions.
7. Record the governance repository, version, and release commit.
8. Leave adoption status as `proposed` unless explicit human approval evidence
   has been supplied and the governance process allows activation at this
   stage.
9. Do not predict the target project's future commit SHA.
10. Do not write a self-referential baseline commit into the same commit it is
    intended to identify.
11. Run the pinned release's validators.
12. Produce a complete Git diff summary.
13. Stop without committing or pushing unless separately authorized.

If an existing file differs from its managed template, do not overwrite it
silently. Produce a three-way reconciliation report containing:

- current project content;
- required governance content;
- proposed merged result;
- unresolved semantic conflicts.

## Spec Kit handling

GitHub Spec Kit is a prerequisite of Nexora Governance v1.0 and must be used at
a pinned compatible release. The skill must read
`manual/07-spec-kit-standard.md` before planning initialization or
reconciliation.

If Spec Kit is already present:

- preserve `.specify/` and `specs/`;
- preserve active feature artifacts;
- report conflicts with scaffold-managed locations;
- do not relocate, rename, duplicate, or recreate native artifacts;
- do not replace the native constitution without review and Project Owner
  approval;
- confirm compatibility before adding `specs/README.md`.

If Spec Kit is absent:

- report the prerequisite as unsatisfied;
- identify the pinned compatible version required by the governance package;
- keep installation and `specify init` as an explicit, reviewable stage;
- do not install it merely as a side effect of inspection or plan mode;
- in apply mode, install or initialize it only when the user explicitly
  authorizes that planned stage;
- do not create imitation `.specify/` or `specs/` structures.

Nexora adds identifiers, indexes, approval rules, and traceability around Spec
Kit. It must not create competing specifications, plans, tasks, analyses, or
completion records.

## Agent instruction files

Use `AGENTS.md` as the agent-neutral project instruction entry point unless the
pinned governance release defines another rule.

Harness-specific files such as `CLAUDE.md` must remain adapters. They must not
become competing governance authorities.

Do not install or configure any of the following during governance adoption
unless the pinned release requires it and the user explicitly authorizes it:

- Ponytail;
- GitHub Spec Kit;
- MCP servers;
- codebase-memory-mcp;
- Confluence integrations;
- external AI services;
- repository hooks;
- CI/CD workflows.

## Approval model

The default governance mode is `solo`. One named Project Owner performs
product, technical, security, operations, and release review.

Honest approval modes include:

- `owner-self-approval`;
- `enhanced-owner-review`.

The skill may prepare approval evidence and checklists but must not record an
approval mode, approver, or date until the Project Owner explicitly supplies or
confirms it.

For new projects, use:

- `prompts/01-new-project-bootstrap.md` for scaffold and agent setup;
- `prompts/04-governance-adoption-review.md` for readiness review.

For existing projects, use:

- `prompts/02-existing-project-read-only-audit.md`;
- `prompts/03-governance-migration-plan.md`;
- `prompts/04-governance-adoption-review.md`.

Prompts assist execution but remain subordinate to the instructions and manual.

## Upgrade mode

For an existing adoption:

1. Read the current adoption record.
2. Resolve the currently adopted governance version and release commit.
3. Resolve the requested new version and release commit.
4. Read `CHANGELOG.md`, `VERSION.md`, and all required migration and release notes between those versions.
5. Compare `project-template/`, instructions, prompts, managed templates, schemas, validators, compatibility requirements, and generated-artifact rules.
6. Identify project-local customizations and approved exceptions.
7. Produce an impact report before proposing changes.
8. Classify changes as:
   - required;
   - recommended;
   - optional;
   - conflicting;
   - deprecated;
   - removed.
9. Preserve project-specific approved content.
10. Require a reviewed upgrade plan before applying changes.

Do not skip versions or migrations when the governance release requires an
ordered upgrade path.

## Validation phase

Run all validators supplied by the pinned governance release.

At minimum, verify:

- all required adoption files exist;
- required metadata is present and schema-valid;
- the governance version is pinned;
- the governance release commit is recorded;
- the configured governance source is sanitized;
- the complete central manual was not copied unnecessarily;
- no duplicate specification or feature-planning system was created;
- no adoption document claims approval that was not supplied;
- no accepted ADR, RFC, or active specification was modified unexpectedly;
- no credentials, tokens, private keys, cookies, or secrets were written;
- no credential-bearing URLs were introduced;
- no unexpected files were overwritten;
- no unplanned executable hooks were installed;
- project-level and harness-specific agent files respect authority precedence;
- the Git diff contains only planned changes;
- generated links and references resolve where locally verifiable;
- the worktree remains recoverable using the documented rollback procedure.

If validation fails, do not describe the adoption as complete. Report the
failure, preserve evidence where allowed, and recommend the smallest safe
corrective action.

## Package-specific validation

In addition to release-supplied validators, verify:

- the package release and commit are immutable and recorded;
- `MANIFEST.json` validation passed before scaffold use;
- the complete `project-template/` contents, including hidden files, were
  considered by the plan;
- customization markers are either resolved or explicitly blocked;
- `CENTRAL-GOVERNANCE-REFERENCE.md` identifies the adopted release correctly;
- `docs/governance/governance-adoption.md` records the selected version and tag;
- new-project adoption used prompt 01 and readiness review prompt 04;
- existing-project adoption used prompts 02 and 03 before migration and prompt
  04 for readiness;
- no legacy content was moved, merged, rewritten, archived, or deleted before
  migration-map approval;
- OpenCode or Codex live configuration was created only from its approved
  example and contains no credentials;
- conditional tools remain disabled unless explicitly approved;
- Spec Kit owns `.specify/`, `specs/`, and native SDD records;
- generated `instructions/README.html` was not edited as source;
- `MANIFEST.json` was not manually modified as ordinary source content.

## Rollback

The adoption plan must include rollback instructions appropriate to the
operation.

Before a modification, capture:

- the starting branch;
- the starting commit;
- the list of pre-existing uncommitted files;
- the reviewed plan identifier;
- the files that will be created or modified.

Do not use destructive rollback commands such as `git reset --hard` or
`git clean -fd` unless the user explicitly authorizes them after reviewing the
impact.

Prefer a dedicated branch and ordinary Git restoration of only the files
created or modified by the reviewed plan.

## Completion report

Report:

- mode executed;
- target project;
- target branch and starting commit;
- adoption classification;
- governance source type;
- sanitized governance source;
- governance version;
- resolved governance release commit;
- reviewed plan identifier, if any;
- files created;
- files modified;
- files preserved;
- conflicts detected;
- validators executed;
- validation results;
- validation not performed;
- assumptions;
- unresolved decisions;
- approvals still required;
- whether the worktree was modified;
- whether a commit or push occurred;
- rollback guidance;
- recommended next governed action.

Do not describe adoption as complete until all validation and approval
requirements from the pinned governance release are satisfied.

## Recommended first use

For the first adoption run in any target project, use local source mode and
planning only.

Obtain the project identity from explicit user input or approved repository
metadata:

- project name;
- project short name;
- project code;
- repository identifier;
- project owner;
- primary agent harness, when applicable;
- model router and pinned model route, when applicable.

Do not assume or hard-code project-specific values in this reusable skill.

Use the reusable configuration template at:

`templates/adoption-config.yaml`

Populate required project fields in a temporary working copy or in the
release-defined project governance location. Do not modify the central template
with target-project values.

Recommended invocation intent:

```text
Adopt Nexora Governance into this project using the trusted local governance
checkout.

Resolve and verify the exact governance release tag and commit, inspect the
target project, and generate an adoption plan only.

Do not access the network, modify project files, install additional tools,
configure external integrations, commit, push, merge, or approve the adoption.

Stop after reporting the proposed changes, conflicts, missing inputs,
validation requirements, approval gates, and rollback plan.
```
