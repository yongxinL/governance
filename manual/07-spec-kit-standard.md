# 07. Spec Kit Standard

**Part II** · Owns: Spec Kit workflow ownership, native structure, installation and initialization, constitution reconciliation, one active integration, workflow stages, existing-project use, native artifact preservation, the `bug` extension (limits B1-B9), other extensions, version-sensitive guidance.

> **Version-sensitive guidance.** Verified 2026-10-12 against the official Spec Kit documentation (github.github.com/spec-kit) and the github/spec-kit repository. No specific release number is fixed by this governance release; each project pins `<SPEC_KIT_VERSION>` in its tooling register and re-verifies commands against that version.

## 7.1 Ownership

GitHub Spec Kit owns the constitution workflow, specify, clarify, plan, checklists, tasks, analysis, implement, convergence, and all native feature artifacts. Nexora adds identifiers, indexes, approval gates, and evidence rules around them.

## 7.2 Installation

Use an official channel only, pinned:

```bash
# Example: install from the official repository at a release tag
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git@<SPEC_KIT_VERSION>
# Example: or from PyPI at a pinned version
uv tool install specify-cli==<SPEC_KIT_VERSION_WITHOUT_V>
specify version
```

Record the version in `docs/governance/tooling-adoption-register.md`.

## 7.3 Initialization

```bash
# Example: initialize in the current repository for the primary agent
specify init --here --integration <SPEC_KIT_INTEGRATION_KEY>
```

- Use `--integration` (the older `--ai` flag is deprecated). Always pass it explicitly; non-interactive runs otherwise default to GitHub Copilot.
- `--force` merges into a non-empty directory and may replace files at managed paths. Use it only after a reviewable baseline commit, and review the resulting diff.
- Git branching workflows are provided by the optional `git` extension and are not installed by default.
- Nexora never pre-creates `.specify/` or `specs/`.

## 7.4 Constitution reconciliation

1. Initialize Spec Kit; it generates the native constitution (location per the pinned version, typically under `.specify/memory/`).
2. Run the native constitution command with `SPEC-KIT-CONSTITUTION-TEMPLATE.md` as input, incorporating Nexora principles truthfully; do not invent standards the project has not adopted.
3. Owner reviews and approves the native constitution; commit (`docs(spec): approve project constitution`, example).
4. Delete `SPEC-KIT-CONSTITUTION-TEMPLATE.md` from the project root unless a documented reason to retain it is recorded in `documentation-exceptions.md`.

## 7.5 One active integration

Spec Kit supports multiple installed integrations and switching. Nexora permits **one active integration at a time**, matching the declared primary agent and recorded in the adoption record. Changing it follows [chapter 19](19-agent-switching-and-handoffs.md). Some integrations share skill directories (Codex uses `.agents/skills/`) and are not multi-install safe; review generated diffs on every integration change.

## 7.6 Workflow stages

| Stage | Native command (dot form) | Nexora status | Nexora addition |
|---|---|---|---|
| Constitution | `speckit.constitution` | Required at adoption | Reconciliation (7.4) |
| Specify | `speckit.specify` | Required for material change | Allocate `SPEC-NNN`, FR/NFR/AC IDs |
| Clarify | `speckit.clarify` | Recommended; required when ambiguity is found | Owner decides material questions |
| Plan | `speckit.plan` | Required | Owner approves plan |
| Checklist | `speckit.checklist` | Optional; recommended for high-risk | None |
| Tasks | `speckit.tasks` | Required | Traceability analysis |
| Analyze | `speckit.analyze` | Recommended; required for high-risk | Pre-implementation gate |
| Implement | `speckit.implement` | Required | Implementation authorization |
| Converge | `speckit.converge` | Required before completion | Owner acceptance |

Invocation syntax differs by integration (for example `/speckit.plan`, `/speckit-plan`, or `$speckit-plan` for Codex skills). Spec Kit treats its entry points as independent processes; Nexora requires the stages marked Required for material change.

## 7.7 Spec Kit bug extension

The official bundled `bug` extension (`specify extension add bug`) is **approved when relevant** within these limits:

| # | Limit |
|---|---|
| B1 | Scope is simple, single-cause defects restoring already intended or specified behaviour. New or changed observable behaviour, business rules, interfaces, security, data, or migration requires SDD with a specification. |
| B2 | If assessment reveals multiple causes, unclear intended behaviour, or a specification gap or conflict, stop and escalate to SDD or an investigation. Never patch specifications through `bug`. |
| B3 | `speckit.bug.assess` is read-only; the owner reviews `assessment.md` before any fix. |
| B4 | `speckit.bug.fix` requires prior owner authorization (`owner-self-approval`). An AI agent cannot authorize it. |
| B5 | The fix stays within assessed scope; any logged deviation returns to the owner. |
| B6 | `test.md` is defect-level evidence; `partial` and `failed` are not completion; `verified` is not approval. |
| B7 | Records remain in `.specify/bugs/<slug>/`, unmoved and unrenamed; the slug is the handle; reference affected `SPEC-NNN-FR/AC` where applicable. |
| B8 | Commit the three records as evidence summaries; do not commit raw logs or traces. |
| B9 | Install per project, pinned to the adopted Spec Kit version, recorded in the tooling register with removal steps. |

## 7.8 Other extensions, presets, bundles, and workflows

| Component | v1.0 status |
|---|---|
| Official `bug` extension | Approved when relevant (7.7) |
| Official `bugfix` bundle and workflow | Not approved (candidate for a later minor release) |
| Official `assess` extension | Not approved (candidate); use investigations and RFCs |
| Official `git` extension | Approved when relevant, after tooling-register entry |
| `agent-context` managed block | Permitted; see [chapter 18](18-ai-agent-standard.md) |
| Community extensions and presets | Not approved unless individually reviewed (prompt 20) |
| Community `bugfix` extension (patches spec, plan, tasks) | Prohibited (violates NX-5) |

## 7.9 Existing projects

Follow the official existing-project guidance: baseline commit and adoption branch, `specify init --here --force --integration <key>`, review diff, constitution from principles already true for the repository, and a bounded first change. Do not make "document the entire system" the first feature.

## 7.10 Native artifact preservation

Never relocate, rename, merge, or delete native artifacts to match Nexora conventions. Nexora identifiers live inside content and indexes. Spec Kit upgrades are tooling changes recorded in the register, with the diff reviewed before commit.
