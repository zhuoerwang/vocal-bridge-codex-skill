---
name: login
description: Authenticate with Vocal Bridge using your API key. Use when the user wants to connect Codex to their Vocal Bridge agent.
---

Authenticate with Vocal Bridge to manage your voice agent.

## Prerequisites

First check if the CLI is installed:

```bash
which vb || command -v vb
```

If not found, install it:

```bash
pip install --upgrade vocal-bridge
```

## Login

Run: `vb auth login <api_key>`

If no API key is provided, tell the user they need to provide their API key. Example:

```
login vb_your_api_key_here
```

The API key can be found on the agent detail page at https://vocalbridgeai.com
