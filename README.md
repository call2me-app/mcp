<p align="center"><img src="assets/logo.png" width="96" alt="Call2Me"></p>

<h1 align="center">Call2Me MCP</h1>

<p align="center">Give your AI assistant a real phone line.</p>

<p align="center">
  <a href="https://cursor.com/en/install-mcp?name=call2me&config=eyJ1cmwiOiAiaHR0cHM6Ly9tY3AuY2FsbDJtZS5hcHAvbWNwIn0="><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add to Cursor" height="32"></a>
  <a href="https://insiders.vscode.dev/redirect/mcp/install?name=call2me&config=%7B%22type%22%3A%20%22http%22%2C%20%22url%22%3A%20%22https%3A//mcp.call2me.app/mcp%22%7D"><img src="https://img.shields.io/badge/VS_Code-Install_MCP-0098FF?logo=visualstudiocode&logoColor=white" alt="Install in VS Code" height="32"></a>
</p>

Call2Me is a hosted [Model Context Protocol](https://modelcontextprotocol.io) server. Connect it once and Claude, ChatGPT, Cursor, VS Code, Gemini CLI or any MCP client can:

- **Place real phone calls** with an AI voice agent, end them, and read the transcript afterwards
- **Run a live two-way interpreter** between two people who share no language — 31 languages, over a browser link or the phone
- **Build voice agents** — prompt, language, voice and model
- **Buy and bind phone numbers** in 21 countries
- Check **campaigns, scheduled calls, call history and wallet balance**

Endpoint: `https://mcp.call2me.app/mcp` (Streamable HTTP)

## Connect

| Client | How |
|---|---|
| **Claude** (claude.ai / Desktop) | Settings → Connectors → *Add custom connector* → paste the endpoint |
| **ChatGPT** | Settings → Apps & Connectors → Developer mode → *Create* → paste the endpoint |
| **Claude Code** | `claude mcp add --transport http call2me https://mcp.call2me.app/mcp` |
| **Cursor** | Click *Add to Cursor* above |
| **VS Code** | Click *Install in VS Code* above |
| **Gemini CLI** | `gemini extensions install https://github.com/call2me-app/mcp` |
| **Codex** | `codex mcp add call2me --url https://mcp.call2me.app/mcp` |
| **Cline** | MCP Servers → Remote Servers → URL `https://mcp.call2me.app/mcp` (see [llms-install.md](llms-install.md)) |

On first use you sign in to Call2Me in the browser (OAuth 2.1 with PKCE). New accounts get **$5 of free credit**, no card needed.

## Tools (37)

| Area | Tools |
|---|---|
| Account | `call2me_profile`, `call2me_get_wallet`, `call2me_get_pricing` |
| Calls | `call2me_make_outbound_call`, `call2me_end_call`, `call2me_list_calls`, `call2me_get_call`, `call2me_get_call_transcript` |
| Voice agents | `call2me_list_agents`, `call2me_get_agent`, `call2me_create_agent`, `call2me_update_agent`, `call2me_delete_agent`, `call2me_create_voice_session` |
| Live interpreter | `call2me_list_interpreters`, `call2me_get_interpreter`, `call2me_create_interpreter`, `call2me_update_interpreter`, `call2me_delete_interpreter`, `call2me_start_interpreter_call`, `call2me_enable_interpreter_web`, `call2me_end_interpreter_web`, `call2me_get_interpreter_web_status`, `call2me_create_interpreter_passcode`, `call2me_list_interpreter_calls` |
| Phone numbers | `call2me_list_allowed_countries`, `call2me_search_numbers`, `call2me_checkout_number`, `call2me_purchase_number`, `call2me_bind_number`, `call2me_unbind_number`, `call2me_release_number`, `call2me_list_phone_numbers` |
| Scheduling | `call2me_create_schedule`, `call2me_list_schedules`, `call2me_cancel_schedule`, `call2me_list_campaigns` |

## Safety

- **Your API key never reaches the model.** The server uses OAuth; tools cannot read or return the key.
- **Read-only access is available** — grant only `call2me:read` and nothing can be created, changed or charged.
- Tools that place a real, charged call or spend money are annotated as such, and the server instructs the model never to guess a phone number or an assistant.

## Pricing

Pay as you go, no subscription: AI voice agent from $0.10/min, live interpreter from $0.25/min, phone numbers $5/month. See [call2me.app/pricing](https://call2me.app/pricing).

## Links

- Docs: [call2me.app/docs/mcp](https://call2me.app/docs/mcp)
- Official MCP Registry: `app.call2me/mcp`
- Website: [call2me.app](https://call2me.app)

This repository holds connection metadata for MCP clients and plugin directories; the server itself is hosted by Call2Me.
