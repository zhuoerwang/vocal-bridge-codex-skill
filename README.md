# Vocal Bridge Skills for Codex

Unofficial, personal-use fork unless Vocal Bridge requests otherwise.

Version: 0.1.0

Manage your Vocal Bridge voice agents directly from Codex. View call logs, update prompts, stream debug events, and more.

## Installation

### Option A: Copy Skills Into Codex

```bash
git clone https://github.com/zhuoerwang/vocal-bridge-codex-skill.git
cp -R vocal-bridge-codex-skill/skills/* ~/.codex/skills/
```

Restart Codex to pick up the new skills.

### Option B: Use Codex Skill Installer

If you use the `skill-installer` skill, install from this repo and the `skills/` subfolder.

## Getting Started

1. **Get your API key** from your agent detail page at [vocalbridgeai.com](https://vocalbridgeai.com)

2. **Login** to connect Codex to your agent:
   ```
   login vb_your_api_key_here
   ```

3. **Verify connection**:
   ```
   status
   ```

## Commands

| Skill | Description |
|---------|-------------|
| `login [api_key]` | Authenticate with your API key |
| `status` | Check authentication status |
| `agent` | Show agent information |
| `logs [session_id]` | View call logs or session details |
| `download <session_id>` | Download call recording audio |
| `stats` | Show call statistics |
| `prompt [show\|set]` | Manage system prompt |
| `config [show\|set\|edit\|options]` | Manage all agent settings |
| `debug` | Stream real-time debug events |
| `setup` | Install CLI if needed |
| `help` | Show all commands |

## Examples

### View Call Logs

```
# List recent calls
logs

# Show last 50 failed calls
logs -n 50 --status failed

# View specific call transcript
logs 550e8400-e29b-41d4-a716-446655440000
```

### Download Call Recordings

```
# Download recording for a session
download 550e8400-e29b-41d4-a716-446655440000

# Download with custom filename
download 550e8400-e29b-41d4-a716-446655440000 -o call.ogg
```

### Manage Prompts

```
# View current prompt
prompt show

# Update prompt (will guide you through the process)
prompt set
```

### Manage Agent Configuration

```
# View all agent settings
config show

# View settings as JSON
config show --json

# Discover valid options for a setting (IMPORTANT: do this before changing settings)
config options voice          # by setting name
config options "TTS Model"    # by label (same as UI)
config options audio          # all settings in a category

# Update specific settings
config set --style Focused
config set --debug-mode true
config set --hold-enabled true --hangup-enabled true

# Edit full configuration in $EDITOR
config edit
```

### Debug Live Calls

```
# Stream debug events (requires debug mode enabled)
debug
```

## Prerequisites

The plugin automatically installs the Vocal Bridge CLI when needed. You can also install it manually:

```bash
pip install vocal-bridge
```

## Requirements

- Codex (recent version)
- Python 3.9+ (for CLI)
- A Vocal Bridge account with a deployed agent

## Links

- [Vocal Bridge Dashboard](https://vocalbridgeai.com)
- [Documentation](https://vocalbridgeai.com/docs/developer-guide)
- [CLI on PyPI](https://pypi.org/project/vocal-bridge/)

## License

Apache-2.0
