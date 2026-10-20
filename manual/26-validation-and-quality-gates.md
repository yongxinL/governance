# 26. Validation and Quality Gates

**Part VI** · **Owns:** project approval gates with entry and exit criteria, pre-implementation gate, task traceability, convergence, release readiness, documentation checks, package release gates, finding severity.

## 26.1 Project gate sequence

```
Governance baseline adopted -> Product intent approved -> Specification approved
-> Technical plan approved -> Task and traceability analysis passed
-> Implementation authorized -> Verification passed -> Convergence completed
-> Release approved
```

Apply gates proportionately: trivial low-risk maintenance needs only a passing test suite and a reviewed commit. Material changes require explicit owner approval at each applicable gate. High-risk changes require `enhanced-owner-review`.

## 26.2 Gate definitions

| Gate | Required inputs | Required checks | Evidence | Next actions permitted | Reopen when |
|---|---|---|---|---|---|
| G-A Governance baseline | Scaffold, adoption record | Prompt 04 | Adoption commit | Product work | Governance upgrade |
| G-B Product intent | Vision, requirements | Prompt 05 | Approval fields | Specification | Product change |
| G-C Specification | Native spec with SPEC IDs | Prompt 07, clarify | Approval fields, index baseline | Plan | Controlled change |
| G-D Plan | Native plan | Prompt 11 | Approval in plan or commit | Tasks | Spec change, design change |
| G-E Tasks and traceability | Native tasks | Native analyze, prompt 12 | Analysis result summary | Pre-implementation | Plan or spec change |
| G-F Implementation authorized | All above | Prompt 13 | Owner instruction recorded in PR or commit | Implement | Blocking discovery |
| G-G Verification | Tests, evidence | Prompt 16 | Verification summary | Converge | Failed verification |
| G-H Convergence | Native converge | Prompt 17 | Convergence outcome | Release | Divergence found |
| G-I Release | Release record | Prompt 18 | Release approval, tag | Deploy | Release defect |

Owner responsibility at every gate is approval or documented waiver. A waiver is a one-time deviation recorded in the affected artifact; it cannot waive NX-1 to NX-6.

## 26.3 Pre-implementation gate

Pass only when: applicable authority has been read; specification and plan are approved; tasks trace to requirements; required tools are registered; no unresolved conflict, ambiguity, or security uncertainty remains; rollback exists for risky changes.

## 26.4 Documentation checks (projects)

Structural (indexes present, required files present), content (metadata, controlled statuses, no unexplained authoring markers), links (relative links resolve), semantic (no competing authorities, indexes match artifacts). Use prompt [19](../prompts/19-documentation-validation.md).

Unexplained authoring markers include the strings `TODO`, `TBD`, `Coming soon`, `Write this section`, `Add details`, and `Lorem ipsum`. Approved customization markers use angle brackets, for example `<PROJECT_NAME>`.

## 26.5 Package release gates (central governance)

| Gate | Verifies |
|---|---|
| 1 Structure | Required tree present; every scaffold directory indexed; no `.specify/`, `specs/`, specification template, phase template, `.gitkeep`, temporary, cache, or secret files; hidden `.codex/` present |
| 2 Content completeness | Substantive chapters, prompts, templates; no unexplained authoring markers; customization markers identified; examples labelled; no invented project facts |
| 3 Governance consistency | Historical `D1`-`D20` governance decision labels preserved as written; no silent renumbering or supersession |
| 4 Authority and duplication | No competing authorities or duplicated authoritative content |
| 5 Security and tooling | No credentials; conditional tools disabled; tool controls documented |
| 6 Links, indexes, identifiers | Internal links resolve; indexes complete; identifier formats consistent |
| 7 Generated artifacts and manifest | HTML fingerprint correct; manifest complete and exact |
| 8 ZIP and release readiness | Single root, safe paths, clean extraction matches manifest |

### 26.5.1 Gate outcomes and approval

Every gate and every individual check within it records exactly one canonical
outcome: `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN`, or `NOT_APPLICABLE`, as defined in
[chapter 13](13-testing-evidence-and-verification.md#1311-canonical-check-outcomes-and-their-mapping).

- A check that was not performed is `NOT_RUN`. It is never `PASS`.
- An unavailable prerequisite, missing tool, or missing dependency is `BLOCKED`,
  and its cause is recorded. It is never silently passed.
- Optional maturity cannot offset a failed mandatory control. A project may not
  trade a gate failure for optional improvements.
- Every mandatory gate must be `PASS` before release approval is requested.
  `FAIL` or `BLOCKED` on any mandatory gate stops the release.

Validation evidence must record, per check: the command or mechanism used, the
result, the paths or artifacts examined, and any limitation that affects
conclusion. A gate marked `NOT_RUN` is not a passed gate.

A validator reports a **recommendation**. Release approval is a separate Project
Owner decision ([chapter 05](05-lifecycle-ownership-and-approvals.md)). Passing
every gate is a precondition for requesting approval, never the approval itself.

### 26.5.2 Cross-specification coordination in validation

Where a governed cross-specification delivery plan coordinates several
specifications or systems, validation may assess the coordination itself:
dependency order, migration and rollback windows, release sequencing, operational
readiness, and owner checkpoints ([chapter 12](12-planning-and-cross-specification-delivery.md)).

The coordination artifact is validated as coordination only. It never replaces a
native feature plan and never contains a competing feature task list. Validation
of a delivery plan must not be read as validation of each participating feature;
those remain validated through their own native artifacts and evidence.

## 26.6 Finding severity

| Severity | Meaning | Examples |
|---|---|---|
| Blocking | Prevents release or gate passage | Missing required file, broken authoritative link, duplicate specification authority, invalid hash, credential exposure, governance contradiction, unsafe ZIP path |
| Major | Resolve before release unless reclassified with documented rationale | Missing cross-reference, tool-default inconsistency, incorrect template path, incomplete prompt controls, orphaned governed document |
| Minor | Non-material wording or formatting | Typographical issues |

### 26.7 Cross-specification delivery coordination

The native Spec Kit plan remains authoritative for each feature. When chapter
12 triggers apply, an approved cross-specification delivery plan may coordinate
multiple specifications, releases, systems, migrations, dependencies, and
owner checkpoints. It does not replace native plans, contain feature tasks, or
restate requirements.
