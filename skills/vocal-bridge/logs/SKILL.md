---
name: logs
description: View call logs for the Vocal Bridge voice agent. Can list recent calls or show details of a specific session including transcript.
---

View call logs for the voice agent.

First ensure CLI is installed:

```bash
pip install --upgrade vocal-bridge
```

## List Recent Logs

If the user provides no arguments or only flags, list recent logs and pass those flags through:

```bash
vb logs [flags]
```

Common options:
- `-n 50` - Show 50 logs (default 20)
- `--status completed` - Filter by status (completed/failed/abandoned/in_progress)
- `--json` - Output as JSON

## View Session Details

If the user provides a UUID (session ID), show details:

```bash
vb logs <session_id>
```

This shows:
- Session ID and status
- Start/end time and duration
- Message count
- Caller phone and direction
- Full transcript
- Error message (if failed)
- Recording availability (if available, use the `download` skill with the session ID)

Use `--json` flag for machine-readable output.
