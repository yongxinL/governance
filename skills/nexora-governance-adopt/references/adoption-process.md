# Nexora Governance Adoption Process

## Purpose

This document defines the reusable process for adopting, validating, repairing,
or upgrading a released Nexora Governance baseline in any target project.

It supports the `nexora-governance-adopt` skill. If this reference conflicts
with instructions in the selected pinned governance release, the pinned release
is authoritative.

## Principles

1. **Versioned reference**: adopt an immutable governance release, not a moving
   branch.
2. **Central authority**: retain the complete governance framework in the
   central Nexora Governance repository.
3. **Project overlay only**: add only the project-specific adoption artifacts
   required by the selected release.
4. **Plan before apply**: generate and review a dry-run plan before modifying a
   target project.
5. **Human approval**: an AI agent may prepare and validate adoption artifacts,
   but may not approve governance adoption, exceptions, ADRs, RFCs, or its own
   work.
6. **Least privilege**: governance retrieval requires read access only.
7. **No credential handling**: authentication is configured outside the skill.
8. **Reviewable changes**: apply adoption on a dedicated branch and retain a
   complete file-level diff.
9. **Deterministic validation**: use release-supplied schemas, scripts, and
   validators where available.
10. **Reversible operation**: record the starting state and provide a
    non-destructive rollback procedure.

## Roles

### Project owner

The project owner:

- supplies or approves project identity;
- selects the governance release;
- reviews the adoption plan;
- resolves project-specific conflicts;
- approves adoption and exceptions;
- authorizes commits, pushes, merges, and releases.

### AI coding agent

The AI coding agent may:

- inspect the target project;
- inspect a pinned governance release;
- prepare an adoption plan;
- render release-provided project overlays;
- identify conflicts and missing inputs;
- run authorized validators;
- report evidence, limitations, and resulting differences.

The AI coding agent may not:

- invent project or governance metadata;
- approve governance adoption;
- approve exceptions, ADRs, or RFCs;
- weaken higher-authority requirements;
- access or manage credentials;
- silently overwrite governed artifacts;
- claim unperformed validation;
- commit, push, merge, or tag unless separately authorized.

### Nexora Governance repository

The central governance repository provides:

- released governance documents;
- the authoritative adoption and upgrade model;
- project-overlay templates;
- schemas and validation rules;
- migration instructions;
- reusable governance skills and scripts.

### Target project

The target project stores only its project-local adoption layer, including the
release reference, source-of-truth assignments, project-specific exceptions,
tooling records, and required adoption evidence.

## Required inputs

Before planning adoption, obtain:

```yaml
project:
  name: required
  short_name: required
  code: required
  repository: required
  owner: required
  root: required

governance:
  source_type: local-or-git
  source: required
  version: required-immutable-release

adoption:
  mode: inspect-plan-apply-validate-or-upgrade
  branch: required-for-apply-or-upgrade

agents:
  primary_harness: required-if-agent-files-are-managed
```

Do not infer approval dates, approvers, releases, commits, exceptions, or tool
adoption states.

## Governance source modes

### Local source mode

Local mode is preferred for the first adoption. Use a trusted,
pre-authenticated local checkout.

Example:

```text
~/.local/share/nexora/governance
```

Verify:

```bash
git -C "$GOVERNANCE_PATH" status --short
git -C "$GOVERNANCE_PATH" remote get-url origin
git -C "$GOVERNANCE_PATH" tag --list
git -C "$GOVERNANCE_PATH" rev-parse "<release>^{commit}"
```

Do not modify the local governance checkout. Do not access the network in local
mode unless the user explicitly requests an update.

### Remote Git source mode

Remote mode may use the user's existing SSH agent or operating-system-backed
Git credential helper.

Use a clean, credential-free repository URL. The skill must not request,
inspect, log, or store credentials.

Perform a non-destructive access check before cloning:

```bash
git ls-remote <sanitized-url> <release-tag>
```

Clone into an operating-system temporary directory, check out the selected
release in detached mode, and remove the temporary checkout after use unless
the governance release requires retention of sanitized evidence.

## Adoption lifecycle

```text
REQUESTED
    ↓
INSPECTED
    ↓
PLANNED
    ↓
PLAN_REVIEWED
    ↓
APPLIED
    ↓
VALIDATED
    ↓
OWNER_APPROVED
    ↓
BASELINE_RECORDED
    ↓
ACTIVE
```

An operation may also end as:

```text
BLOCKED
CONFLICT
VALIDATION_FAILED
CANCELLED
NOT_APPLICABLE
```

## Phase 1: Inspect the target project

Record:

- project root;
- project identity discovered from approved metadata;
- current branch and commit;
- configured remotes;
- worktree status;
- protected or default branch status;
- existing governance artifacts;
- existing agent-neutral and harness-specific instruction files;
- existing Spec Kit or other approved SDD artifacts;
- existing ADR and RFC locations;
- existing product, architecture, testing, operations, and release documents;
- existing tooling records and exceptions;
- potential duplicate authorities;
- files that may conflict with managed templates.

Classify the project as:

```text
new-adoption
existing-compliant-adoption
incomplete-adoption
upgrade-required
conflict
not-applicable
```

## Phase 2: Inspect the governance release

Verify:

- exact release tag;
- exact release commit;
- clean checkout;
- approved remote;
- adoption instructions;
- project-overlay templates;
- schemas and validators;
- migration and release notes;
- required approvals;
- compatibility requirements.

Reject a moving reference such as `main`, `master`, `HEAD`, or `latest` for an
applied adoption.

## Phase 3: Produce the adoption plan

The plan must contain:

- immutable plan identifier or checksum;
- target project identity;
- governance release tag and commit;
- adoption classification;
- files to create, each classified:
  - `SAFE_AUTOMATIC` - creates a new scaffold file that conflicts with nothing
    and whose content is fully determined by approved inputs;
  - `CAREFUL_CONSOLIDATION` - merges or rewrites existing material, requiring a
    reviewed diff and a recorded rationale;
  - `OWNER_DECISION` - depends on a judgement the Project Owner must make, such
    as which of two conflicting sources stays authoritative;
- files to update;
- files to preserve, including all approved hidden files;
- files requiring reconciliation;
- conflicts and missing inputs;
- required owner decisions;
- validation commands;
- approval gates;
- rollback steps;
- readiness to apply.

Planning must not modify authoritative target-project files.

Existing-project work follows inspect, plan, approve, apply, then validate. Never
delete or overwrite existing authoritative content before migration authority is
established. Preserve approved hidden files when copying the scaffold.

Approval fields remain `Pending` until a real Project Owner decision occurs. A
scaffold initialization date is not an adoption approval date, and preparation by
an agent is not approval by the Project Owner.

## Phase 4: Review gate

Stop for review when:

- the plan has not been reviewed;
- project identity is incomplete;
- the governance reference is mutable;
- approval evidence is missing;
- an exception is required;
- the target is a protected branch;
- the worktree contains unrelated changes;
- a governed file requires semantic reconciliation;
- release instructions conflict with the target-project state.

Only an authorized human or governance-defined approval mechanism may approve
the plan.

## Phase 5: Apply the reviewed plan

Before applying:

1. verify the reviewed plan identifier;
2. verify the dedicated governance branch;
3. verify the starting commit and worktree state;
4. confirm no new blocking conflict exists.

During application:

- use release-provided templates and generators;
- create only the planned project overlay;
- preserve project-specific approved content;
- do not overwrite governed files silently;
- do not install unrelated tooling;
- retain `proposed` status until valid approval is supplied;
- do not invent a future baseline commit;
- do not commit or push unless separately authorized.

## Phase 6: Validate

Run all validators required by the pinned release and the checks in
`validation-checklist.md`.

For every validation, record:

- command or mechanism;
- result;
- relevant sanitized output;
- remediation required;
- checks not performed and why.

A required failure prevents completion.

## Phase 7: Owner approval and baseline

The owner reviews:

- generated and modified files;
- governance source, tag, and release commit;
- project-specific exceptions;
- tooling states;
- validation evidence;
- full Git diff.

Use a two-step baseline where required:

1. create and review the adoption implementation commit;
2. record the reviewed commit as the adoption baseline in a later approval
   update.

Do not create a self-referential baseline field.

## Phase 8: Completion

Adoption becomes active only when:

- the governance release is pinned;
- required project-overlay files are valid;
- blocking conflicts are resolved;
- validation passes;
- required approval exists;
- the reviewed baseline is recorded according to governance.

Report one of:

```text
planned
applied-but-unvalidated
validated-awaiting-approval
active
blocked
failed
```

## Upgrade process

For an upgrade:

1. read the current adoption record;
2. resolve current and requested tags and commits;
3. inspect all required migration notes;
4. compare templates, schemas, validators, and requirements;
5. identify project customizations and exceptions;
6. produce an impact report;
7. classify changes as required, recommended, optional, conflicting,
   deprecated, or removed;
8. create a reviewed migration plan;
9. apply on a dedicated branch;
10. validate before approval.

Do not skip ordered migrations required by the governance release.

## Rollback

Before applying, capture:

- starting branch;
- starting commit;
- pre-existing uncommitted paths;
- reviewed plan identifier;
- planned created and modified files.

Prefer restoring only files affected by the reviewed plan. Do not run
`git reset --hard`, `git clean -fd`, or another destructive operation without
explicit owner authorization after impact review.

## Completion report

Every run must report:

- mode;
- target project and branch;
- starting commit;
- governance source type and sanitized source;
- governance version and release commit;
- adoption classification;
- plan identifier;
- created, modified, preserved, and conflicted files;
- validation performed and omitted;
- approvals still required;
- whether the worktree changed;
- whether commit or push occurred;
- rollback guidance;
- next governed action.
