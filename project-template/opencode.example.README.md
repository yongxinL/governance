# OpenCode Project Configuration Example

Non-authoritative supporting guidance for `opencode.json.example`.

## What this file is

`opencode.json.example` is an **example**. Its presence does not activate
anything: OpenCode reads `opencode.json`, not `opencode.json.example`. Nothing is
installed, enabled, trusted, or connected until a person copies the file to
`opencode.json` and the application is started.

## Before copying

1. Review the example against the OpenCode version actually installed. The
   published schema at `opencode.ai/config.json` may flag fields the runtime
   accepts, including `mcp.servers` and `disabled`; verify rather than assume.
2. Confirm the project has adopted a governance release
   ([governance-adoption.md](docs/governance/governance-adoption.md)).
3. Confirm the primary agent is recorded in the adoption record.

Copy to `opencode.json` in the project root only after review. Remove the
`.example` suffix; do not keep both files with different content.

## Target and precedence

Precedence, lowest to highest: user configuration, project `opencode.json`,
`.opencode/opencode.json`, then `OPENCODE_CONFIG_CONTENT`. Configurations merge,
and a higher-precedence server entry replaces the whole server object rather than
merging field by field. Verify precedence against the installed version before
relying on it.

## Authority and scope

This example never overrides the central manual, project governance records,
Project Owner approval, or native GitHub Spec Kit workflows.

Model, provider, account, and credential preferences are **user-level**. Keep them
in user configuration, not in this project file. A committed project configuration
must not carry a personal account, provider credential, or model preference.

## Permission, state, and task authorization

Three separate controls. This example demonstrates none of them by being present.

| Control | Question | Recorded in |
|---|---|---|
| Permission | Is the tool permitted for this project at all? | [docs/governance/approved-tooling.md](docs/governance/approved-tooling.md) |
| Lifecycle and configuration state | Is it installed, configured, and enabled right now? | [docs/governance/tooling-adoption-register.md](docs/governance/tooling-adoption-register.md) |
| Task-level authorization | Is this specific action approved right now? | Project Owner instruction at the time of action |

Set `disabled` to `false` only after an entry exists in the tooling adoption
register. A tool that is permitted and enabled is still **not** authorized for
destructive, privileged, production, publication, deployment, credential-bearing,
or external-write actions; those always need explicit owner authorization.

## Integrations in this example

All conditional servers are disabled by default.

| Server | Type | Default | Notes |
|---|---|---|---|
| `context7` | Remote | Disabled | Requires data-handling acceptance. Uses `{env:CONTEXT7_API_KEY}`. For OAuth, remove `oauth` and `headers` and sign in through `/mcps`. |
| `openaiDeveloperDocs` | Remote | Disabled | Enable only when OpenAI or Codex work is relevant. Sends queries to a public documentation service; do not include proprietary code. |
| `playwright` | Local | Disabled | Requires a resolved `<PLAYWRIGHT_MCP_VERSION>` and mandatory `--isolated`. |

`codebase-memory-mcp`, Ponytail, Forgejo write integration, deployment, and
infrastructure integrations are intentionally **absent**. Add them only through
tool adoption review, and record the entry.

## Credentials and environment variables

Secret values never enter this file. Reference them by environment variable:

- `CONTEXT7_API_KEY` for Context7.

Never substitute a literal key, token, password, cookie, or private key. Do not
embed credentials in URLs. Prefer an SSH agent, credential helper, or approved
secret manager.

## Version markers to resolve

| Marker | Resolve to |
|---|---|
| `<PLAYWRIGHT_MCP_VERSION>` | A pinned `@playwright/mcp` version |

An unresolved marker makes the Playwright entry non-functional. The vendor's
`@latest` examples are not acceptable in committed configuration because they
make behaviour unreproducible.

## Playwright requirements

`--isolated` is mandatory. It uses an in-memory profile so nothing is written to
disk. The default persistent profile retains logins and cookies and is not
permitted. Never point Playwright at a personal browser profile.

`--headless` is the default; use headed mode only when visual review is explicitly
required.

## Local and remote execution

Review what each integration sends where:

- **Remote** servers transmit data to an external service. Confirm the data is
  appropriate to send before enabling.
- **Local** servers execute on the machine with the project's filesystem access.
  Review readable and writable paths, especially any browser profile, download
  directory, or credential store.

## Failure behavior

If an integration fails, stop using it and fall back to approved core tools. Do
not disable security controls to make a tool work. Record the failure and its
impact in the tooling adoption register.

## Validation

After copying and customizing:

1. Confirm the file parses as strict JSON.
2. Confirm every conditional server is still `disabled` until authorized.
3. Confirm no secret value is present and all markers are resolved.
4. Record the actual state in the tooling adoption register.

## Rollback and removal

To remove an integration: delete its server entry from `opencode.json`, revoke any
issued credential at the vendor, remove the environment variable, delete local
state such as caches or indexes, and update the tooling adoption register. Do not
delete the register entry; set its state and record the removal reason.

## Adoption

Adoption is a governed change. Follow
[ADOPTION-INSTRUCTIONS.md](ADOPTION-INSTRUCTIONS.md). Copying this example does
not complete adoption and does not grant approval.
