---
name: download
description: Download call recording for a specific session. Saves the audio file to the current directory.
---

Download the audio recording for a specific call session.

First ensure CLI is installed:

```bash
pip install --upgrade vocal-bridge
```

## Download Recording

The user should provide a session ID (UUID):

```bash
vb logs download <session_id>
```

This downloads the audio file to the current directory with filename `recording_<id>.<format>`.

## Custom Output Path

To save to a specific location, use the `-o` flag:

```bash
vb logs download <session_id> -o /path/to/call.ogg
```

## Notes

- Recordings are only available if the agent has call recording enabled
- Audio format depends on agent configuration (usually ogg or wav)
- Use the `logs` skill with the session ID first to check if a recording is available
