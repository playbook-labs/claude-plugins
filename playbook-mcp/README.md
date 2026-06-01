# Playbook MCP plugin

Connects Claude to your [Playbook](https://www.playbook.com) workspace via the
hosted Playbook MCP server (`https://mcp.playbook.com`), so you can find, move,
copy, tag, and organize assets and boards through natural language.

This plugin only **registers** the MCP server connection — the tools run on the
hosted server, which wraps Playbook's REST API. Connecting authenticates via
Playbook OAuth (no token is stored in this plugin).

## Tools exposed

Asset and board operations including: `list_assets`, `search_assets`,
`ai_search`, `get_asset`, `move_assets`, `copy_assets`, `change_asset_tags`,
`update_asset_status`, `create_board`, `update_board`, `list_boards`,
`list_board_children`, `share_asset`, `share_board`, `create_comment`,
`list_documentation`, `read_documentation`, and more.

## Install

```
/plugin marketplace add /path/to/playbook/.claude/playbook   # if not already added
/plugin install playbook-mcp@playbook
```

Or via CLI:

```
claude plugin install playbook-mcp@playbook
```

## Authenticate

After install, run `/mcp` and complete the Playbook OAuth flow for the
`playbook` server. Tokens do not expire (revoke from your Playbook account
settings).

## Note for local development

If you already registered the server manually (`claude mcp add playbook
https://mcp.playbook.com`), remove that entry to avoid a duplicate connection:

```
claude mcp remove playbook
```
