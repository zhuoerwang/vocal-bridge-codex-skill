---
name: help
description: Show help for Vocal Bridge Codex skills
---

# Vocal Bridge Codex Skills

| Skill | Description |
|---------|-------------|
| `login [api_key]` | Authenticate with API key |
| `status` | Check authentication status |
| `agent` | Show agent information |
| `logs [session_id]` | View call logs |
| `download <session_id>` | Download call recording |
| `stats` | Show call statistics |
| `prompt [show\|set]` | Manage system prompt |
| `config [show\|set\|edit\|options]` | Manage all agent settings |
| `debug` | Stream debug events |
| `setup` | Install CLI if needed |

## Getting Started

1. Get your API key from your agent detail page at https://vocalbridgeai.com
2. Run `login vb_your_api_key` to authenticate
3. Use `agent` to verify connection

## Examples

```
# Login with your API key
login vb_abc123xyz

# Check connection status
status

# View recent call logs
logs

# View last 50 failed calls
logs -n 50 --status failed

# View specific call transcript
logs 550e8400-e29b-41d4-a716-446655440000

# Download call recording
download 550e8400-e29b-41d4-a716-446655440000

# Show call statistics
stats

# View current prompt
prompt show

# View all agent settings
config show

# Show valid options for a setting (ALWAYS do this before changing settings)
config options voice
config options "TTS Model"

# Update agent settings
config set --debug-mode true

# Set session limits
config set --max-call-duration 15
config set --max-history-messages 50

# Edit full config in editor
config edit

# Stream debug events
debug
```

## CLI Installation

The skills can install the CLI when needed. You can also install manually:

```bash
pip install vocal-bridge
```

Or download the standalone script:

```bash
curl -fsSL https://vocalbridgeai.com/cli/vb.py -o vb && chmod +x vb
```

## More Information

- Documentation: https://vocalbridgeai.com/docs/developer-guide
- Dashboard: https://vocalbridgeai.com
- GitHub: https://github.com/vocalbridgeai/vocal-bridge-claude-plugin
