# 23. codebase-memory-mcp Standard

**Part V** · **Owns:** conditional adoption, triggers, local index, include and exclude paths, sensitive-data exclusions, freshness, commit and branch association, UI exposure, source verification, sharing, removal.

> Verified 2026-10-12 against github.com/DeusData/codebase-memory-mcp and PyPI release 0.11.0. Upstream performance figures are first-party claims (project benchmark and the authors' preprint) and are not Nexora guarantees.

## 23.1 Classification

Local · read (source) plus write (local index, and agent configuration during its installer) · no external transmission claimed · no credentials · persistent index. Status: **disabled initially**.

## 23.2 Adoption triggers

Consider only when: the codebase is large enough that file-by-file exploration materially slows work, structural questions (call chains, routes, impact) recur, and the owner accepts the local index footprint. Record measured benefit during a pilot.

## 23.3 Installation controls

- Install a pinned release from the official repository or PyPI.
- The upstream installer writes to agent configuration files. Prefer manual MCP configuration; if the installer is used, review and revert unwanted configuration changes.
- Disable its ADR-management feature for Nexora use; ADRs live only in `docs/architecture/adr/` (NX-1).
- Do not use its team artifact-sharing feature without owner approval.

## 23.4 Index scope

Record in the register: index location, included paths, excluded paths (`.env*`, secrets directories, credentials, data dumps, `node_modules`, build output, vendored binaries, backups), and the ignore file used.

## 23.5 Freshness

Associate the index with a branch and commit. Re-index after branch switches and significant merges. Treat stale results as invalid.

## 23.6 UI exposure

The optional graph UI listens on localhost. Do not bind it to other interfaces or expose it remotely without explicit owner approval.

## 23.7 Verification

Important conclusions (impact analysis, dead-code findings) are verified against current source before acting.

## 23.8 Sharing

Indexes are not committed and not shared outside the owner's machine without approval.

### 23.8.1 Permission, state, and task authorization

This tool obeys the three-way split defined in
[chapter 20](20-developer-tooling-and-security.md#2021-permission-state-and-task-authorization-are-distinct):

- **Permission** - whether this tool is permitted for the project at all,
  recorded in `docs/governance/approved-tooling.md`;
- **Lifecycle and configuration state** - whether it is installed, configured,
  and enabled right now, recorded in
  `docs/governance/tooling-adoption-register.md`;
- **Task-level authorization** - whether this specific action is approved right
  now, given by the Project Owner at the time of action.

An enabled tool is not automatically authorized for every action. Destructive,
privileged, production, publication, deployment, credential-bearing, and
external-write actions always require explicit Project Owner authorization
regardless of configuration state.

## 23.9 Removal

Remove MCP configuration entries, uninstall the binary or package, delete local indexes (upstream uninstall may retain indexes; delete explicitly), update the register. Removal criteria: no measurable benefit in pilot, stale-result incidents, or security concern.
