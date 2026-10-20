# Nexora Governance Adoption Validation Checklist

## Purpose

Use this reusable checklist to validate a planned, applied, repaired, or
upgraded Nexora Governance adoption.

The selected pinned governance release may add or strengthen checks. It remains
authoritative.

## Result values and severity

Each check records exactly one outcome: `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or
`NOT_APPLICABLE`. A check that was not run is `NOT_RUN`, never `PASS`. An
unavailable prerequisite is `BLOCKED`, never silently passed.

Each finding records one severity: `BLOCKING`, `MAJOR`, or `MINOR`. A `BLOCKING`
finding stops adoption or release. Never use percentage scoring that could hide
a failed mandatory control.

## Package integrity

Where `MANIFEST.json` is present, verify and record: a single package root, safe
relative paths, no traversal or absolute paths, approved hidden files preserved,
manifest self-exclusion, every listed path existing, and exact byte size and
SHA-256 per entry. Confirm no distributed file is missing from the manifest other
than the declared self-excluded manifest. Never edit manifest hashes by hand.

Record one result for every applicable check:

- `PASS`
- `FAIL`
- `NOT_APPLICABLE`
- `NOT_RUN`
- `BLOCKED`

`NOT_RUN` and `BLOCKED` require an explanation. A required `FAIL`, `NOT_RUN`, or
`BLOCKED` result prevents the adoption from being described as complete.

## 1. Operation identity

- [ ] Requested mode is recorded: inspect, plan, apply, validate, or upgrade.
- [ ] Target-project name is recorded.
- [ ] Target-project short name is recorded.
- [ ] Target-project code is recorded.
- [ ] Target repository identifier is recorded.
- [ ] Project owner is explicitly identified.
- [ ] Starting branch and commit are recorded.
- [ ] Initial worktree state is recorded.
- [ ] Reviewed plan identifier or checksum is recorded when applicable.

## 2. Governance source

- [ ] Source type is recorded as local or Git.
- [ ] Source path or URL is sanitized.
- [ ] No credential is embedded in the source URL.
- [ ] Configured remote matches the approved governance repository.
- [ ] Requested release tag exists.
- [ ] Release resolves to an immutable commit SHA.
- [ ] Release commit is recorded.
- [ ] Governance checkout is clean.
- [ ] Applied baseline does not use `main`, `master`, `HEAD`, or `latest`.
- [ ] Required release notes and migrations were inspected.
- [ ] Temporary checkouts were removed or retained only as governed,
      sanitized evidence.

## 3. Authentication and secrets

- [ ] Authentication was configured outside the skill.
- [ ] Agent did not request a password, token, key, cookie, or secret.
- [ ] No private-key file or credential store was read.
- [ ] No credential was written to the target project.
- [ ] No credential was written to the governance checkout.
- [ ] No credential appears in logs, diffs, or reports.
- [ ] No credential-bearing URL was introduced.
- [ ] TLS verification remained enabled.
- [ ] No insecure transport fallback occurred.
- [ ] Authentication failures were sanitized.

## 4. Branch and repository safety

- [ ] Apply or upgrade did not run on a protected default branch.
- [ ] Dedicated governance branch was used where required.
- [ ] Unrelated uncommitted work was absent or explicitly protected.
- [ ] Unreviewed repository hooks were not run.
- [ ] No unexpected remote or submodule was configured.
- [ ] No destructive cleanup command was used.
- [ ] Rollback steps target only planned paths.
- [ ] Commit, push, merge, tag, and pull-request actions match explicit
      authorization.

## 5. Adoption model

- [ ] Project uses the versioned-reference model.
- [ ] Complete central governance manual was not copied unnecessarily.
- [ ] Only release-defined project-overlay artifacts were created or updated.
- [ ] Adoption record identifies governance repository, tag, and commit.
- [ ] Governance release commit is distinct from project baseline commit.
- [ ] Adoption document does not predict its own future commit SHA.
- [ ] Adoption status reflects actual approval state.
- [ ] No approval was invented or inferred.

## 6. Authority and source of truth

- [ ] Authority precedence is documented or inherited from the release.
- [ ] Organizational governance authority is unambiguous.
- [ ] Project governance authority is unambiguous.
- [ ] ADR and RFC authority is unambiguous.
- [ ] Specification and planning authority is unambiguous.
- [ ] Project source-of-truth locations are declared.
- [ ] Generated, published, cached, derived, and temporary artifacts are not
      presented as authoritative.
- [ ] No duplicate authority was introduced.
- [ ] Unresolved authority conflicts are blocking.

## 7. Managed files and reconciliation

- [ ] Every created file appears in the reviewed plan.
- [ ] Every modified file appears in the reviewed plan.
- [ ] Planned preserved files remain unchanged.
- [ ] Existing governed files were not silently overwritten.
- [ ] Semantic conflicts received a reconciliation report.
- [ ] Accepted ADRs and RFCs were not unexpectedly modified.
- [ ] Active specifications were not unexpectedly modified.
- [ ] Approved exceptions were preserved.
- [ ] Generated links resolve where locally verifiable.
- [ ] Required metadata conforms to release-provided schemas.

## 8. Agent instructions

- [ ] Agent-neutral instruction entry point follows the release standard.
- [ ] Harness-specific instruction files remain adapters.
- [ ] Harness adapters do not become competing governance authorities.
- [ ] Instructions point to authoritative governance and project artifacts.
- [ ] Instructions do not claim approval authority.
- [ ] Instructions require honest validation reporting.
- [ ] Instructions do not expose credentials.

## 9. SDD-tool coexistence

- [ ] Existing approved SDD artifacts were preserved.
- [ ] No competing specification system was created.
- [ ] No competing feature planning or task system was created.
- [ ] Existing constitution or equivalent was not replaced without review.
- [ ] An absent SDD tool was not installed implicitly.
- [ ] Any SDD-tool installation is a separate reviewable change.

For GitHub Spec Kit projects specifically:

- [ ] Existing `.specify/` content was preserved.
- [ ] Existing `specs/` content was preserved.

## 10. Tooling boundaries

- [ ] Tooling-adoption register reflects actual states.
- [ ] Proposed tools are not described as adopted.
- [ ] Deferred tools were not installed.
- [ ] MCP servers were not installed implicitly.
- [ ] External integrations were not configured implicitly.
- [ ] CI/CD workflows and repository hooks were not added unexpectedly.
- [ ] Tool versions are pinned where required.
- [ ] Tool authority remains subordinate to governance and accepted decisions.

## 11. Upgrade-specific checks

- [ ] Current adopted version and commit were resolved.
- [ ] Requested version and commit were resolved.
- [ ] Required intermediate migrations were identified.
- [ ] Release notes between versions were reviewed.
- [ ] Template, schema, validator, and requirement changes were compared.
- [ ] Project customizations were identified.
- [ ] Approved exceptions were checked for continued validity.
- [ ] Changes were classified as required, recommended, optional, conflicting,
      deprecated, or removed.
- [ ] Upgrade plan was reviewed before application.

## 12. Validation execution

- [ ] All release-supplied required validators were run.
- [ ] Validator commands or mechanisms are recorded.
- [ ] Validator release context is recorded.
- [ ] Sanitized results are retained as required.
- [ ] Failures are reported accurately.
- [ ] Checks not run are listed with reasons.
- [ ] Final Git diff was reviewed.
- [ ] Final Git diff contains only planned changes.
- [ ] `git diff --check` or equivalent passed.
- [ ] Final worktree state is recorded.

## 13. Approval and completion

- [ ] Required owner approval exists.
- [ ] Approval identity and date are recorded only after approval.
- [ ] Required exceptions are approved and recorded.
- [ ] Reviewed adoption baseline commit is recorded correctly.
- [ ] Adoption is not described as active before validation and approval.
- [ ] Completion status is one of: planned, applied-but-unvalidated,
      validated-awaiting-approval, active, blocked, or failed.
- [ ] Completion report identifies unresolved decisions.
- [ ] Completion report identifies the next governed action.
- [ ] Rollback guidance is included.

## Validation report template

```markdown
# Governance Adoption Validation Report

## Summary

- Project:
- Project short name:
- Project code:
- Repository:
- Owner:
- Operation mode:
- Target branch:
- Starting commit:
- Governance source type:
- Governance release:
- Governance release commit:
- Adoption classification:
- Plan identifier:
- Final status:

## Results

### Passed

- ...

### Failed

- ...

### Not run

- Check:
- Reason:
- Impact:

### Blocked

- Check:
- Blocking condition:
- Required decision:

## Files

### Created

- ...

### Modified

- ...

### Preserved

- ...

### Conflicted

- ...

## Security review

- Credentials exposed: No/Yes
- Credential-bearing URLs introduced: No/Yes
- Unexpected external access: No/Yes
- Unexpected hooks or tools installed: No/Yes

## Approval

- Owner approval required: Yes/No
- Approval recorded: Yes/No
- Approved by:
- Approved at:

## Rollback

- Starting commit:
- Affected paths:
- Safe rollback procedure:

## Next action

...
```
