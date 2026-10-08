# Installing the Call2Me MCP server

Call2Me is a **hosted** MCP server — there is nothing to clone, build or run locally.

1. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "call2me": {
      "type": "streamableHttp",
      "url": "https://mcp.call2me.app/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

2. On the first tool call the client opens a browser window to sign in to Call2Me (OAuth 2.1 with PKCE). No API key is pasted anywhere; the model never sees one. New accounts get $5 of free credit without a card.

3. Verify with a read-only tool, e.g. `call2me_profile` or `call2me_get_wallet`.

Notes for the agent:
- Do not add any tool to `autoApprove`. `call2me_make_outbound_call`, `call2me_create_schedule` and `call2me_purchase_number` spend real money; the user must confirm each one.
- Never guess a phone number or an assistant id — ask the user.
