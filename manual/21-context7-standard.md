# 21. Context7 Standard

**Part V** · Owns: Context7 purpose, approved use, current integration guidance, external query handling, query minimization, authentication, configuration scope, authority boundaries, removal.

> Verified 2026-10-12 against context7.com documentation and github.com/upstash/context7. Version: hosted service; no pinned version.

## 21.1 Purpose

Context7 retrieves current, version-specific library documentation and code examples for the agent.

## 21.2 Classification

Remote · read-only · transmits queries externally · requires API key or OAuth · non-destructive · non-privileged. Status: **approved for use after project data-handling acceptance**, recorded in the tooling register.

## 21.3 Current integration (OpenCode v2)

```jsonc
// Example: opencode.json(c), mcp.servers entry, API key via environment variable
"context7": {
  "type": "remote",
  "url": "https://mcp.context7.com/mcp",
  "oauth": false,
  "headers": { "CONTEXT7_API_KEY": "{env:CONTEXT7_API_KEY}" },
  "disabled": true
}
```

OpenCode v2 remote servers use OAuth by default; to use OAuth instead, omit `oauth: false` and the header, and sign in through `/mcps`. Set `disabled` to `false` only after acceptance. Note: on 2026-10-12 the published schema at `opencode.ai/config.json` did not yet validate all v2 fields; the runtime accepted them.

## 21.4 Current integration (Codex)

```toml
# Example: .codex/config.toml (trusted project). Keep disabled until accepted.
[mcp_servers.context7]
url = "https://mcp.context7.com/mcp"
bearer_token_env_var = "CONTEXT7_API_KEY"
enabled = false
```

Verify the exact Codex keys against the installed Codex version before enabling. The vendor's OAuth endpoint is `https://mcp.context7.com/mcp/oauth`.

Do not use the vendor's automatic setup command (`ctx7 setup`) in governed projects; it modifies agent configuration and installs skills or rules. Configure manually.

## 21.5 Query handling

- Treat every query as disclosed to a third-party hosted service. Retention terms were not verified at release; consult the vendor's current terms during data-handling acceptance.
- Use focused queries naming a library and concept only.
- Never include proprietary source, credentials, personal data, internal hostnames, or unnecessary project context.

## 21.6 Authority boundaries

Retrieved documentation is external information. It is not proof of project implementation and does not override specifications, ADRs, or the pinned tool version's actual behaviour.

## 21.7 Removal

Remove the server entry from project configuration, revoke the API key at the vendor, remove `CONTEXT7_API_KEY` from the environment, update the register.
