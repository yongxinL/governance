# Nexora Governance Authority Model

## Purpose

This document defines reusable authority precedence and source-of-truth
principles for projects adopting Nexora Governance.

It supports the `nexora-governance-adopt` skill. The selected pinned governance
release remains authoritative when release-specific rules differ from this
reference.

## Authority precedence

Apply the following order from highest to lowest authority:

1. Applicable law, security obligations, contractual requirements, and
   organizational controls
2. The pinned Nexora Governance release
3. Accepted project governance and approved project exceptions
4. Accepted RFCs and Architecture Decision Records
5. Approved product requirements and feature specifications
6. Approved implementation plans, tasks, and acceptance criteria
7. Repository source code, configuration, tests, and retained evidence
8. Project-level agent instructions such as `AGENTS.md`
9. Harness-specific adapters, skills, hooks, and plugins
10. Session prompts and informal working notes

A lower-authority artifact must not override a higher-authority artifact.

If two authoritative artifacts conflict and no documented precedence or scope
rule resolves the conflict, stop and request an authorized decision.

## Organizational governance authority

The central Nexora Governance repository owns:

- organization-wide governance principles;
- governance release definitions;
- adoption and upgrade requirements;
- canonical governance templates and schemas;
- governance validation rules;
- authority and exception mechanisms;
- reusable governance automation.

A target project adopts a specific released version. It does not copy the
complete central governance body unless the selected release explicitly
requires a packaged artifact.

## Project governance authority

The target project's governance overlay owns project-specific matters such as:

- adopted governance release and exact release commit;
- project identity and ownership;
- project source-of-truth assignments;
- approved project tooling;
- approved project exceptions;
- adoption evidence and baseline;
- project-specific governance indexes and links.

A project overlay may specialize behavior only where the central governance
release permits it. It may not silently weaken or contradict central controls.

## Decision authority

### ADRs and RFCs

Accepted ADRs and RFCs are authoritative for their declared scope.

An AI agent may draft or analyse a decision, but may not:

- accept it;
- supersede it;
- alter its outcome silently;
- implement a conflicting architecture without a governed change.

### Specifications

Approved specifications define required behavior and acceptance criteria for a
bounded delivery scope.

Implementation convenience, agent instructions, or session prompts must not
remove requirements from an approved specification.

### Plans and tasks

Plans and tasks organize execution. They remain subordinate to accepted
decisions and approved specifications.

They may clarify delivery details, but cannot redefine approved scope without a
governed change.

## Tool authority

Tools remain subordinate to governance and approved project artifacts.

### Spec-driven development tools

Where an SDD tool is adopted, it owns only its approved native artifacts and
workflow locations.

Project governance may add traceability, metadata, indexes, and approval
evidence. It must not create a competing specification or planning authority.

For GitHub Spec Kit, its native locations are normally `.specify/` and
`specs/`, subject to the version and configuration adopted by the project.

### AI coding agents

AI coding agents are analysis and implementation assistants, not approvers.

They may:

- inspect;
- compare;
- draft;
- propose;
- implement approved work;
- perform authorized validation;
- report evidence, uncertainty, and limitations.

They may not:

- approve their own output;
- alter authority precedence;
- invent approval evidence;
- claim validation that was not performed;
- resolve policy conflicts silently;
- bypass security controls.

### Skills, plugins, hooks, and MCP servers

These provide procedures, integrations, or enforcement mechanisms. They remain
below accepted project artifacts in authority.

They must not:

- redefine governance;
- introduce unapproved external access;
- remove validation or security requirements;
- modify accepted ADRs or specifications silently;
- grant themselves approval authority.

### Model routers and model providers

A model router and its selected model are execution infrastructure only. They
do not define governance or project truth.

A model change must not alter approved requirements, decisions, or validation
obligations. Pin a validated model route for governance-sensitive work when
required by project policy.

## Source-of-truth principles

Every governed information type must have one declared authoritative location.

Supporting copies must be identified as one of:

- generated;
- published;
- cached;
- derived;
- non-authoritative;
- temporary.

If two locations both appear authoritative, stop automation and resolve the
ownership conflict before synchronizing them.

## Generic project boundaries

The following model is a starting point. The target project's approved
source-of-truth register must define the actual paths and tools.

### Central governance

```text
Authority: pinned Nexora Governance release
Location: central private governance repository
```

### Project governance adoption

```text
Authority: approved project governance overlay
Location: release-defined project governance location
```

### Product vision and scope

```text
Authority: approved product documentation
Location: project source-of-truth register
```

### Feature specifications, plans, and tasks

```text
Authority: approved artifacts from the adopted SDD workflow
Location: adopted tool's canonical locations
```

### Architectural decisions

```text
Authority: accepted ADRs and RFCs
Location: release-defined project architecture locations
```

### Source code and configuration

```text
Authority: reviewed repository content
Location: project source-of-truth register
```

### Tests and evidence

```text
Authority: executed validation and retained evidence
Location: project source-of-truth register
```

### Operations and releases

```text
Authority: approved operational and release artifacts
Location: project source-of-truth register
```

### Published or synchronized representations

```text
Role: derived or published representation
Authority: explicitly declared source artifact
Drift handling: project-specific governed procedure
```

### AI instructions

```text
Project-wide entry point: AGENTS.md or release-defined equivalent
Harness adapters: CLAUDE.md and other tool-specific files
```

Harness adapters must point to project authority. They must not duplicate or
replace it.

## Project-specific extensions

A target project may define extra source-of-truth categories, including:

- curated knowledge;
- external publication targets;
- infrastructure state;
- data schemas;
- API contracts;
- operational runbooks;
- compliance evidence;
- design assets;
- generated packages.

These categories belong in the target project's source-of-truth register, not
in this reusable skill reference.

## Conflict handling

### Direct contradiction

Two authoritative artifacts require incompatible outcomes.

Action:

- stop implementation;
- identify both artifacts and their scopes;
- report their authority levels;
- obtain an authorized decision.

### Duplicate authority

Two locations claim ownership of the same information type.

Action:

- stop synchronization or publication;
- choose one authority through governance;
- mark other locations generated, derived, or deprecated;
- document migration and drift handling.

### Stale lower-authority artifact

A prompt, adapter, template, or working note conflicts with a newer accepted
artifact.

Action:

- follow the higher-authority artifact;
- report the stale item;
- propose a bounded correction;
- do not silently rewrite unrelated content.

### Unapproved exception

The requested action requires deviation from governance, but no approved
exception exists.

Action:

- stop;
- draft a proposed exception if requested;
- identify risks and compensating controls;
- wait for approval.

## Approval authority

Only an authorized human or governance-defined approval mechanism may approve:

- governance adoption or upgrade;
- project exceptions;
- ADRs and RFCs;
- production publication or deployment authority;
- protected-branch merges;
- permanent credential or permission expansion.

An AI-generated approval statement is not approval evidence.

## Evidence authority

Validation evidence must identify:

- what was checked;
- the command or mechanism used;
- when it was performed;
- the applicable version or commit;
- sanitized results;
- checks omitted and why.

A narrative claim such as "all checks passed" is insufficient when those checks
were not executed or retained as required.

## Change discipline

Before a governed change:

1. identify authoritative artifacts;
2. identify applicable accepted decisions;
3. identify required approvals;
4. identify validation obligations;
5. identify rollback boundaries.

After a governed change:

1. report files and systems changed;
2. report decisions applied;
3. report validation performed and omitted;
4. record unresolved conflicts;
5. retain required evidence;
6. identify the next governed action.
