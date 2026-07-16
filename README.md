# ainpc - AINPCEngine CLI

Create, talk to, and manage AI-powered NPCs from the command line. Built for coding agents.

## Install

```bash
npm install -g ainpc-cli
```

## Get Your API Key

```bash
ainpc signup "My Studio" --email you@studio.com --password ********
```

Creates your studio and auto-saves an `npk_` API key. Then log in at https://ainpcengine.com and add a card to start the **7-day free trial** ($0 today, plans from $29/mo). Or sign up at https://ainpcengine.com/auth/register and generate a key in Studio Dashboard → API Keys.

## Quick Start

```bash
# Login (one time)
ainpc login --key YOUR_API_KEY --game my-rpg

# Create an NPC
ainpc create "Grok the Blacksmith" --role merchant --traits gruff,loyal

# Talk to them
ainpc say NPC_ID "Got any swords?"

# AI-generate a full NPC (NPC Persona)
ainpc generate --role guard --name "Captain Voss"

# List all NPCs
ainpc list

# Check status
ainpc status
```

## Per-Project Config

```bash
ainpc login --local --key YOUR_KEY --game my-rpg   # saves to .ainpc/config.json
ainpc login --key YOUR_KEY --game my-rpg           # saves to ~/.ainpc/config.json
ainpc config                                       # show active config
```

Local config overrides global. Add `.ainpc/` to your `.gitignore`.

## Agent Integration

Add to your CLAUDE.md, .cursorrules, .clinerules, or .windsurfrules:

```
Use the ainpc CLI for NPC management.
Config auto-loaded from .ainpc/config.json or AINPC_API_KEY env.
Run ainpc --help for full reference.
```

## MCP Server

49 tools for AI agents: NPC CRUD, dialogue, game events, persona generation, studio account, usage and billing.

**Local (stdio):**

```json
{ "mcpServers": { "ainpcengine": { "type": "stdio", "command": "ainpc", "args": ["mcp-serve"] } } }
```

Requires `npm install -g ainpc-cli` + `ainpc login --key npk_YOUR_KEY --game my-rpg` (or `AINPC_API_KEY` env).

**Remote (SSE, zero install)** — for Claude Web and other web-based agents:

```json
{ "mcpServers": { "ainpcengine": { "type": "sse", "url": "https://mcp.ainpcengine.com/sse",
  "headers": { "Authorization": "Bearer npk_YOUR_API_KEY" } } } }
```

No key yet? Connect keyless — the remote server starts in onboarding mode and an agent can self-signup via the `ainpc_signup` tool.

## Commands

```
ainpc create "Name" --role R          Create NPC
ainpc list                            List all NPCs
ainpc show NPC_ID                     Show detail
ainpc say NPC_ID "message"            Talk to NPC
ainpc generate --role guard           AI-generate NPC
ainpc speak NPC_ID "text"             NPC voice (TTS)
ainpc status                          Quick overview
ainpc --help                          Full reference
```

## Environment Variables

```
AINPC_API_KEY=your-key
AINPC_GAME_ID=my-rpg
AINPC_BASE_URL=https://ainpcengine.com   # optional
```

## Links

- Platform: https://ainpcengine.com
- Docs: https://ainpcengine.com/docs
- Demo: https://ainpcengine.com/demo
