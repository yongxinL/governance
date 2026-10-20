# 25. Playwright and Remote Integrations

**Part V** · Owns: Playwright MCP use cases, browser isolation, authentication, screenshots and traces, unsafe execution, Forgejo integration, remote writes, production access, infrastructure integrations, privileged tools.

> Verified 2026-10-12 against playwright.dev/mcp documentation. Pin a specific `@playwright/mcp` version; the vendor's examples use `@latest`, which is not acceptable in committed configuration.

## 25.1 Playwright MCP use cases

Exploratory checks of local or test environments, reproducing UI defects, and drafting automated tests. Committed Playwright tests remain the repository evidence; MCP sessions are temporary working evidence.

## 25.2 Classification

Local process controlling a browser · read and write against websites · may transmit data to visited sites · may hold session state · potentially destructive on live sites. Status: **disabled initially**.

## 25.3 Browser isolation

- Always run with `--isolated` (in-memory profile; nothing written to disk). The default persistent profile retains logins and cookies and is not permitted.
- Never use the browser extension mode that connects to the owner's personal browser.
- Restrict navigation with `allowedOrigins` to the test environment.

Example (OpenCode v2):

```jsonc
"playwright": {
  "type": "local",
  "command": ["npx", "@playwright/mcp@<PLAYWRIGHT_MCP_VERSION>", "--isolated", "--headless"],
  "disabled": true
}
```

## 25.4 Authentication

Use dedicated test accounts. Do not use production authentication unless the owner explicitly authorizes it for a bounded task. The `--secrets` redaction feature is a convenience, not a security boundary.

## 25.5 Screenshots, traces, downloads, state

Presume them sensitive. Write them to an ignored output directory, do not commit, and delete after use unless a redacted summary is needed as evidence.

## 25.6 Unsafe execution

Disable capabilities not required (for example `devtools`, `config`) and do not enable arbitrary code execution features unless specifically required and recorded.

## 25.7 Forgejo integration

Disabled or read-only initially. Use a dedicated least-privilege token scoped to the project. Writes, publications, merges, tags, releases, workflow dispatch, deployment, and deletion require owner authorization per action.

## 25.8 Remote writes and production access

Any tool action with external side effects requires prior owner authorization. Production credentials are never given to agents by default.

## 25.9 Infrastructure and privileged tools

Deployment, infrastructure (cloud consoles, container hosts, DNS, reverse proxies), and identity-provider integrations are disabled initially and require an RFC or register entry with explicit scope, dry-run capability where available, and a rollback procedure.
