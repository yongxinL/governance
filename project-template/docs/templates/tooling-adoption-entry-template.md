# Tooling Adoption Entry Template

> **Template (non-authoritative).** Copy the block below into `docs/governance/tooling-adoption-register.md` and assign the next `TA-NNN` label. Review using the tool adoption review prompt (central prompt 20).

This entry records **lifecycle and configuration state** only. Three controls are
distinct and must not be collapsed:

- **Permission** - whether the tool is permitted at all. Recorded separately in
  `approved-tooling.md`.
- **Lifecycle and configuration state** - what this entry records: Planned,
  Pilot, Enabled, Disabled, Removed.
- **Task-level authorization** - whether this specific action is approved now.
  Given by the Project Owner at the time of action, never implied by this entry.

A tool marked `Enabled` is still not authorized for destructive, privileged,
production, publication, deployment, credential-bearing, or external-write
actions. Those always require explicit owner authorization.

Leave `Verified on`, `State`, and the approval fields unresolved until they are
real. Do not pre-populate an approval, an installation result, or a verification
date that did not occur.

```markdown
### TA-NNN: <Tool name>

| Field | Value |
|---|---|
| Purpose | |
| Permission basis | Entry in approved-tooling.md |
| Official source | |
| Version (pinned) | |
| Verified on | YYYY-MM-DD |
| Installation scope | Project / user / system |
| Configuration location | |
| Project access | Paths readable / writable |
| Operation | Local / remote |
| Data transmission | What is sent, to whom |
| Credentials | Mechanism and location (never values) |
| Write capability | |
| Destructive capability | |
| Persistence | Caches, indexes, browser state |
| Context overhead | |
| Authority | Non-authoritative |
| State | Planned / Pilot / Enabled / Disabled / Removed |
| Approved by / mode / date | *Completed on real approval only* |
| Pilot metrics | Optional |
| Failure behavior | Stop or continue with approved core tools |
| Network targets | Hosts or services contacted |
| Review trigger | Version, permission, incident, or removal trigger |
| Task authorization | Separate owner authorization where required |
| Removal criteria | |
| Removal procedure | Config entries, binaries, skills or plugins, caches and indexes, credential revocation |
```
