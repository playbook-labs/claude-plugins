# Playbook plugins for Claude Code

A Claude Code plugin marketplace for [Playbook](https://www.playbook.com).

## Add this marketplace

```
/plugin marketplace add playbook-labs/claude-plugins
```

## Plugins

### `playbook-mcp`

Connects Claude to your Playbook workspace via the hosted Playbook MCP server
(`https://mcp.playbook.com`) — find, move, copy, tag, and organize assets and
boards through natural language.

```
/plugin install playbook-mcp@playbook
```

Then run `/mcp` and complete the Playbook OAuth flow. See
[`playbook-mcp/README.md`](./playbook-mcp/README.md) for details.
