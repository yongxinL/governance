# 22. OpenAI Developer Documentation MCP Standard

**Part V** · Owns: purpose, read-only classification, current setup, relevance conditions, data handling, authority boundaries, removal.

> Verified 2026-10-12 against developers.openai.com Docs MCP documentation. Hosted service; no pinned version.

## 22.1 Purpose

Search and read OpenAI developer documentation (developers.openai.com, platform.openai.com, learn.chatgpt.com) from the agent.

## 22.2 Classification

Remote · read-only · documentation-only (does not call the OpenAI API) · no credentials · non-destructive. Status: **approved when relevant**.

## 22.3 Relevance conditions

Enable only when the project works with the OpenAI API, Codex configuration, ChatGPT apps, or other OpenAI platform features.

## 22.4 Current setup

```toml
# Example: Codex, project .codex/config.toml (official example uses ~/.codex/config.toml)
[mcp_servers.openaiDeveloperDocs]
url = "https://developers.openai.com/mcp"
```

```jsonc
// Example: OpenCode v2 mcp.servers entry
"openaiDeveloperDocs": {
  "type": "remote",
  "url": "https://developers.openai.com/mcp",
  "disabled": true
}
```

Prefer project scope over the vendor's user-level example so the server is not enabled for unrelated projects. Do not add the vendor's "always use" `AGENTS.md` snippet unconditionally; condition it on OpenAI relevance.

## 22.5 Data handling

Queries go to OpenAI's public documentation server. Do not include proprietary code or secrets.

## 22.6 Authority boundaries

Documentation results are external guidance, not project authority.

## 22.7 Removal

Delete the server entry (or `codex mcp remove openaiDeveloperDocs` where available), update the register.
