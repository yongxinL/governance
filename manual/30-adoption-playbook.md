# 30. Adoption Playbook

**Part VI** · Owns: new-project adoption, full scaffold copy, customization, environment configuration, Spec Kit initialization, constitution reconciliation, baseline commits, first specification, existing-project adoption, governance upgrades, adoption completion.

## 30.1 New-project adoption

**Stage 1 - Copy the scaffold.** Copy `project-template/` contents into the project root including hidden files:

```bash
# Example
cp -a <central-governance-checkout>/project-template/. <project-root>/
```

**Stage 2 - Customize.** Replace markers in: `docs/governance/governance-adoption.md`, `source-of-truth-register.md`, `approved-tooling.md`, `tooling-adoption-register.md`, `documentation-exceptions.md`, `AGENTS.md`, `CENTRAL-GOVERNANCE-REFERENCE.md`. Leave a marker in place, with a note, where a value is genuinely unknown; never invent it.

**Stage 3 - Configure the environment.** Choose `opencode` or `codex`. Copy `opencode.json.example` to `opencode.json` or `.codex/config.toml.example` to `.codex/config.toml`, remove the unused example, keep conditional tools disabled, and keep credentials in the environment. Trust the project in Codex after reviewing its configuration.

**Stage 4 - Product intent.** Create `docs/product/vision.md` and `docs/product/requirements.md` from templates; approve.

**Stage 5 - Initialize Spec Kit** at a pinned version ([chapter 07](07-spec-kit-standard.md)).

**Stage 6 - Reconcile the constitution** and remove the temporary template.

**Stage 7 - Specification index.** Create `specs/README.md` after compatibility verification ([chapter 17](17-indexing-traceability-and-source-of-truth.md)).

**Stage 8 - Baseline commits** (example messages):

```
docs: establish Nexora project governance scaffold
docs(product): define product vision and requirements
docs(spec): approve project constitution
```

Optionally create an annotated tag such as `governance-adopted-v1.0.0` (example).

**Stage 9 - First governed change.** Specify, clarify, plan, checklist (optional), tasks, analyze, implement, optional Ponytail review (if registered), converge, release.

## 30.2 Existing-project adoption

Follow [chapter 28](28-archive-retention-and-migration.md): baseline branch, scaffold without reorganizing, read-only audit, authority first, approved migration map, controlled batches, incremental SDD, completion. Initialize Spec Kit with `--here --force` only after a baseline commit, and review the diff.

## 30.3 Governance upgrades

Follow [chapter 04](04-governance-versioning-and-exceptions.md#42-explicit-adoption). Upgrades never happen implicitly.

## 30.4 Adoption completion

Run prompt [04](../prompts/04-governance-adoption-review.md). When the mandatory controls in [chapter 29](29-audit-conformance-and-maturity.md#292-mandatory-conformance-controls-level-1-baseline) are met, set the adoption state to `Adopted` (or `Adopted with Exceptions`) and commit.
