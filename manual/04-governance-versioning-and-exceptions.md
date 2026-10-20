# 04. Governance Versioning and Exceptions

**Part I** · **Owns:** patch, minor, and major releases; explicit project adoption; exception types; review triggers; emergency corrections; non-exception controls in the exception context.

## 4.1 Release types

| Type | Examples | Project impact |
|---|---|---|
| Patch (x.y.**z**) | Correction, clarification, broken-link repair, non-material wording, example or generated-file correction, tool-syntax correction | No new mandatory obligation |
| Minor (x.**y**.0) | Backward-compatible improvement, new optional template, newly approved capability, new recommended metadata, improved validation, optional tooling guidance | Optional uptake; no breaking obligation |
| Major (**x**.0.0) | Source-of-truth change, workflow-owner change, identifier-meaning change, mandatory structure or approval-model change, artifact-authority change | Requires adoption review and possibly migration |

Every release is published as an immutable annotated tag (`vX.Y.Z`) with a `CHANGELOG.md` entry. Tags are never moved or deleted.

### 4.1.1 Owner-approved release-classification exceptions

The Project Owner may approve publishing a release under a lower version number
than its content would ordinarily warrant. Such an exception must be:

- recorded explicitly in `CHANGELOG.md` and `VERSION.md`;
- limited to backward-compatible, corrective, or optional material;
- free of any new mandatory obligation for adopting projects.

An approved exception never permits a breaking change, a hidden migration
requirement, a weakened foundational control, a change of source-of-truth or
workflow ownership, or a silent alteration of an identifier meaning. If any of
those would result, the release is classified on its actual impact and requires
a separate Project Owner decision.

Release `1.0.1` carries such an approved exception; see `CHANGELOG.md`.

## 4.2 Explicit adoption

Projects adopt each release explicitly:

1. Read the changelog entries between the adopted and target versions.
2. Assess impact on project records, exceptions, and tooling.
3. For a major release, run prompt [04](../prompts/04-governance-adoption-review.md).
4. Update `docs/governance/governance-adoption.md` (version, tag, adoption date, state).
5. Update `CENTRAL-GOVERNANCE-REFERENCE.md`.
6. Commit as `docs(governance): adopt Nexora Governance vX.Y.Z` (example message).

## 4.3 Exception types

| Type | Use | Recorded in |
|---|---|---|
| Temporary exception | A rule cannot be met for a bounded period | `docs/governance/documentation-exceptions.md` |
| Standing project exception | A rule does not fit the project permanently | `docs/governance/documentation-exceptions.md` |
| One-time deviation | A single feature or release departs from a rule | The affected artifact (specification, release record) |

## 4.4 Required fields for continuing exceptions

Rule affected · reason · impact · compensating control · approval (approver, mode, date) · review trigger · resolution condition (temporary exceptions).

## 4.5 Review triggers

Review exceptions on: governance upgrade, expiry of resolution condition, related incident, risk or exposure change, contributor-access change, and every trigger-based audit ([chapter 29](29-audit-conformance-and-maturity.md)).

## 4.6 Emergency corrections

An urgent production correction may proceed before full documentation if delay would cause harm. Within the next working session, the owner records a one-time deviation in the affected release or specification, and completes any required specification, ADR, or lesson. Emergency handling never permits committing secrets or inventing approvals.

## 4.7 Non-exception controls

Exceptions cannot waive controls NX-1 to NX-6 ([chapter 01](01-governance-policy.md#18-foundational-non-exception-controls)). An exception that would do so is invalid.
