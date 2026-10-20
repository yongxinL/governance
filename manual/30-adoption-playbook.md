# 30. Adoption Playbook

**Part VI** · **Owns:** new-project adoption, full scaffold copy, customization, environment configuration, Spec Kit initialization, constitution reconciliation, baseline commits, first specification, existing-project adoption, governance upgrades, adoption completion.

## 30.1 New-project adoption

**Stage 0 - Verify the package.** Confirm the release and its integrity before copying anything: verify the immutable tag or archive checksum, then verify every packaged file against `MANIFEST.json` ([chapter 27](27-generated-files-manifests-and-packaging.md)). Stop if any digest, size, or release identifier mismatches.

The central governance repository location is a required input supplied by the
Project Owner, recorded as `<GOVERNANCE_REPOSITORY_URL>` in project governance
records. The released package deliberately ships no default governance
repository URL, because that value is deployment-specific. Do not copy a manual
into the project; reference the central release instead.

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

Optionally create an annotated adoption tag using the version-neutral pattern
`governance-adopted-vX.Y.Z`. For this release the pattern is
`governance-adopted-v1.0.1`. An adoption tag is a project-local marker and is
distinct from the central release tag.

**Stage 9 - First governed change.** Specify, clarify, plan, checklist (optional), tasks, analyze, implement, optional Ponytail review (if registered), converge, release.

## 30.2 Existing-project adoption

Follow [chapter 28](28-archive-retention-and-migration.md): baseline branch, scaffold without reorganizing, read-only audit, authority first, approved migration map, controlled batches, incremental SDD, completion. Initialize Spec Kit with `--here --force` only after a baseline commit, and review the diff.

## 30.3 Governance upgrades

Follow [chapter 04](04-governance-versioning-and-exceptions.md#42-explicit-adoption). Upgrades never happen implicitly.

## 30.4 Adoption completion

Run prompt [04](../prompts/04-governance-adoption-review.md). When the mandatory controls in [chapter 29](29-audit-conformance-and-maturity.md#292-mandatory-conformance-controls-level-1-baseline) are met, set the adoption state to `Adopted` (or `Adopted with Exceptions`) and commit.

## 30.5 Agent-assisted adoption

The released package may include
`skills/nexora-governance-adopt/SKILL.md`. The skill may assist with package
integrity verification, inspection, planning, scaffold application, validation,
and upgrade impact analysis.

The skill is optional and non-authoritative. It does not replace this playbook,
`README.md`, `instructions/README.md`, `manual/`, the required prompts,
`project-template/`, `MANIFEST.json`, native Spec Kit ownership, or Project Owner
approval.

The skill must:

- read the authoritative governance sources rather than reconstructing policy
  from model memory;
- verify the selected package and its `MANIFEST.json` before applying anything;
- accept project identity and `<GOVERNANCE_REPOSITORY_URL>` as explicit inputs;
- distinguish new-project from existing-project adoption;
- inspect and produce a plan before applying any change;
- preserve hidden files when copying the scaffold;
- stop at Project Owner gates and return owner decisions rather than resolving
  them;
- avoid installing, initializing, or enabling tools as a side effect;
- avoid committing, pushing, merging, tagging, publishing, deploying, or
  approving without explicit authorization.

It must not embed target-project facts or a deployment-specific governance
repository in reusable central content.

When required inputs are missing, the skill stops and reports what is missing.
It must not fall back to an assumed default source.
