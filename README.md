# ainpc - AINPCEngine CLI

Create, talk to, and manage AI-powered NPCs from the command line. Built for coding agents.

## Install

```bash
npm install -g ainpc-cli
```

## Get Your API Key

1. Sign up at https://ainpcengine.com/auth/register ($1 one-time verification)
2. Go to Studio Dashboard > API Keys
3. Generate a key and create a game

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
