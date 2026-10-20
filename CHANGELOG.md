# Changelog

All notable changes to Nexora Governance are recorded here. Each entry corresponds to an immutable release tag. Entries distinguish **governance policy** from **version-sensitive tooling procedures**.

## [1.0.1] - Draft for release · planned tag `v1.0.1`

Project Owner-approved corrective documentation release.

This entry is a work-in-progress record. Items marked *pending* have not been
completed or validated at the time of writing and must not be read as done.

### Verified baseline and release-state corrections

- Verified `1.0.0` source baseline recorded as `d00dcab5f70c083a37d612e48eacb67e38aa272e`.
- `1.0.0` was declared Released on 2026-10-12 in `VERSION.md` at that baseline.
- No `v1.0.0` tag was found locally or on `origin`. This release records that
  truthfully and does not create a retrospective tag.
- Removed the false claim that `v1.0.0` was still under release preparation.

### Root and instructions guidance

- Root README restructured around the active release, with overview, purpose,
  benefits, audience, scope, governance principles, central-versus-project
  authority, solo-owner default, prerequisites, new-project and existing-project
  adoption, daily workflow selection, package navigation, versioning and
  upgrades, security boundaries, package integrity, generated-artifact policy,
  the optional adoption skill, and the change and support process.
- Removed editor-generated HTML markup and hard line breaks where clean
  Markdown is sufficient.
- Corrected stale `v1.1` headings that contradicted the declared release.

### Manual, prompts, and project template

- Manual chapter corrections: malformed headings, escaped Markdown, invalid
  tables, broken lifecycle arrows, malformed examples, broken links,
  contradictory controls, and inconsistent terminology.
- Clarified pending-approval safeguards, verification outcomes including
  `NOT_RUN` semantics, tool permission and task-authorization boundaries, and
  native feature-plan versus cross-specification coordination boundaries.
- Preserved the local-template use of `EXC-NNN` and added an explicit statement
  of its boundary rather than silently creating a new mandatory central
  identifier family.
- Documented the boundary between historical D1-D20 and DEC-001 through DEC-020
  without renumbering durable decisions.
- Prompts standardized to a consistent structure, check outcomes (`PASS`,
  `FAIL`, `BLOCKED`, `NOT_RUN`, `NOT_APPLICABLE`), and finding severities
  (`BLOCKING`, `MAJOR`, `MINOR`). Write prompts require reviewed write scope,
  `git status`, `git diff --check`, complete diff review, actual validation
  reporting, and non-destructive recovery guidance.
- Project template corrected for active release pointers, approval placeholders,
  status vocabulary, and source-of-truth boundaries. No approval evidence is
  pre-populated and no project facts are invented.

### Reusable configuration portability

- Removed the deployment-specific private governance repository URL from
  distributed package content and replaced it with a required project-neutral
  input or marker. The adoption skill must stop with a clear message when no
  governance repository has been supplied, and must not fall back to a
  deployment-specific default.

### Release-classification exception

- The Project Owner approved shipping this corrective scope as `v1.0.1` rather
  than a minor release. Part of this scope would ordinarily be classified as
  minor because it adds optional, backward-compatible material. This is recorded
  as an explicit owner-approved compatibility exception. It introduces no new
  mandatory obligation for adopting projects and does not change source-of-truth
  ownership, workflow ownership, identifier meaning, mandatory approvals, or
  native GitHub Spec Kit ownership.

### Pending

The following have not been performed at the time of writing:

- regeneration of `instructions/README.html` from its Markdown source;
- regeneration of `MANIFEST.json`;
- deterministic release archive build and clean-extraction validation;
- the eight release gates;
- final release authorization, tagging, and publication.

### Upgrade impact

None required. A project adopted on `1.0.0` needs no migration. Corrections apply
to package documentation and do not alter a project's governance obligations.

## [1.0.0] - 2026-10-12 · declared Released · tag `v1.0.0` not found

Initial release. No `v1.0.0` tag was found locally or on `origin`; see the
`1.0.1` baseline notes above.

### Governance policy

- Governance authority, precedence, and foundational non-exception controls (chapter 01).
- Central, versioned adoption model with explicit per-project adoption records (chapters 02, 04, 30).
- Native GitHub Spec Kit ownership of the SDD workflow and its artifacts; prohibition of competing specifications, plans, tasks, analysis, and completion records (chapters 06, 07).
- Project-local stable identifiers: `SPEC-NNN`, `SPEC-NNN-FR/NFR/AC-NNN`, `ADR-NNN`, `RFC-NNN`, `INV-NNN`, `LES-NNN` (chapter 16).
- Git-based baselines and approval evidence (chapter 05).
- Solo-owner default with `owner-self-approval` and `enhanced-owner-review` modes (chapter 05).
- Proportional artifact creation and lifecycle-based evidence retention (chapters 03, 13).
- Distributed indexes and a source-of-truth register (chapter 17).
- Controlled statuses and minimal metadata (chapter 16).
- Read-only, trigger-based audits, domain assessments, and optional maturity levels (chapter 29).
- Eight release gates and finding severities (chapter 26).
- Full project scaffold, 11 templates, and 22 copy-ready prompts.

### Version-sensitive tooling procedures (verified 2026-10-12)

- GitHub Spec Kit: `specify init --integration <key>`, pinned installation, native constitution reconciliation.
- Spec Kit `bug` extension approved when relevant, within limits B1-B9; `bugfix` bundle and `assess` extension listed as candidates; community `bugfix` extension prohibited (chapter 07).
- Spec Kit managed `AGENTS.md` block permitted as a non-authoritative section (chapter 18).
- OpenCode v2 configuration (`mcp.servers`, `disabled`, `{env:NAME}`) and Codex `.codex/config.toml` trusted-project configuration examples.
- Tool standards for Context7, OpenAI Developer Documentation MCP, codebase-memory-mcp, Ponytail, Playwright MCP, and Forgejo integration (chapters 20-25).
