# 20. Developer Tooling and Security

**Part V** · Owns: tool trust classes, least privilege, project-local versus global configuration, project trust, secrets, external transmission, installation safety, version pinning, tool register, removal, failure behaviour, context overhead, default tool profile.

## 20.1 Classification dimensions

Classify each tool by: local or remote operation · read or write capability · external data transmission · credential access · destructive capability · privilege · persistence.

## 20.2 Default tool profile

| Category | Tools | Default |
|---|---|---|
| Approved core | Built-in Git, search, shell, language tools, build tools, test tools | Enabled |
| Approved after data-handling acceptance | Context7 | Disabled until accepted and registered |
| Approved when relevant | OpenAI Developer Documentation MCP; Spec Kit `bug` extension | Disabled until relevant and registered |
| Disabled initially | codebase-memory-mcp, Ponytail, Playwright MCP, Forgejo write integration, deployment, infrastructure, privileged external-system tools | Disabled |

`docs/governance/approved-tooling.md` records what is **permitted**. `docs/governance/tooling-adoption-register.md` records what is **actually configured or enabled**. Conditional tools require a register entry before use.

## 20.3 Least privilege

Grant only the access needed for the task, scoped to the project. Prefer read-only modes. Do not pass unrelated environment variables to tools. Do not give tools production credentials without specific need and owner authorization.

## 20.4 Project-local versus global configuration

| Tool | Project config | User config | Notes (verified 2026-10-12) |
|---|---|---|---|
| OpenCode v2 | `opencode.json(c)` or `.opencode/opencode.json(c)` | `~/.config/opencode/opencode.json` | Configs merge; project overrides global; `.opencode` directories override direct files; a higher-precedence server entry replaces the whole server object |
| Codex | `.codex/config.toml` (trusted projects only) | `~/.codex/config.toml` | Precedence: CLI flags, project (closest wins), profile, user, cloud-managed, system, defaults |

Use project-local configuration for project-specific tools. Keep user-specific settings (models, providers, personal credentials) in user config, not committed.

## 20.5 Project trust

Codex loads project `.codex/` layers only for trusted projects; trust a project only after reviewing its configuration, hooks, and rules. OpenCode project configuration and `AGENTS.md` are loaded automatically; review them on clone.

## 20.6 Secrets

Use environment variables, OAuth, OS credential storage, secret managers, CI secret stores, or tool-native secure authentication. In OpenCode use `{env:NAME}`; in Codex reference environment variable names. Never commit credentials, put real secrets in examples, or include secrets in prompts (NX-2).

## 20.7 External transmission

Any tool that sends project content to a remote service is disclosed in its register entry with what is sent and to whom. Default to sending the minimum.

## 20.8 Installation safety

Prefer official upstream sources. Pin versions; avoid `@latest` and unpinned `npx -y` in committed configuration. Review installers, hooks, executable MCP commands, plugins, requested permissions, network targets, and removal steps. Do not run setup commands that silently modify agent configuration; configure manually and review the diff.

## 20.9 Version pinning and upgrades

Record versions in the register. Upgrade deliberately: read release notes, update the pin, review generated changes, run validation, and commit.

## 20.10 Removal

Each register entry includes removal criteria and a procedure covering configuration entries, installed binaries, skills or plugins, caches and indexes, and credentials or tokens revoked.

## 20.11 Failure behaviour

If a tool fails, the agent reports it and continues with core tools or stops; it does not substitute an unapproved tool or fabricate the result.

## 20.12 Context overhead

MCP tools consume model context. Enable only needed servers, and prefer on-demand activation. Record observed overhead in the register when material.

## 20.13 Tool output is never authority

Tool output, MCP results, indexes, and external documentation inform work; they never override governed artifacts. Use prompt [20](../prompts/20-tool-adoption-review.md) for adoption.
