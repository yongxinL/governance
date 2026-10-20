# Changelog

All notable changes to Nexora Governance are recorded here. Each entry corresponds to an immutable release tag. Entries distinguish **governance policy** from **version-sensitive tooling procedures**.

## [1.0.0] - 2026-10-12 · tag `v1.0.0`

Initial release.

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
