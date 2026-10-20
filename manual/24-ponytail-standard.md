# 24. Ponytail Standard

**Part V** · Owns: conditional classification, review-only pilot, metrics, authority boundaries, prohibited weakening, promotion criteria, removal criteria, first-party benchmark qualification.

> Verified 2026-10-12 against github.com/DietrichGebert/ponytail (release v5.1.0) and ponytail.dev. Ponytail is a ruleset with skills, hooks, and agent plugins that encourages minimal code. Its published benchmark figures are first-party claims, not Nexora guarantees.

## 24.1 Classification

Local ruleset · influences agent behaviour · no external transmission by itself · hooks can inject rules into every session. Status: **disabled initially**.

## 24.2 Review-only pilot

- Use only on demand for review of a completed change (prompt [15](../prompts/15-ponytail-quality-review.md)).
- Do **not** install its session hooks or always-on plugins; always-on mode influences implementation and is outside the pilot.
- Pin the version; record in the register.
- Findings are suggestions dispositioned by the owner.

## 24.3 Metrics

Record per reviewed change: findings raised, findings accepted, defects found, false positives, lines removed through accepted findings, and review time. Pilot across at least five changes before a promotion decision.

## 24.4 Authority boundaries

Ponytail output is non-authoritative. Approved requirements, the constitution, and quality gates prevail.

## 24.5 Prohibited weakening

Ponytail may not be used to remove or weaken: requirements, tests, security controls, accessibility, observability, error handling, recovery, rollback, or documentation. Suggestions doing so are rejected.

## 24.6 Promotion criteria

Promotion beyond review-only (for example, rules active during implementation) requires a register update, recorded pilot metrics showing net benefit, and owner approval; it is a tooling change, not a governance change.

## 24.7 Removal

Remove skills, plugins, and any hooks; delete activation state files; update the register. Removal criteria: net-negative metrics, any prohibited weakening incident, or excessive context overhead.
