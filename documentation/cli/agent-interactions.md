# Agent Interactions

## Interactive Requests

The CLI handles mid-run agent requests inline — no need to switch to the browser for routine flows:

- **Credentials** — a secure in-terminal form for entering secrets
- **OAuth** — opens a browser tab for provider authorisation and waits for the callback
- **MCP servers** — prompts for server URL and connection details

## Platform Guard Notices

Guard verdicts render as distinct bubbles, matching the web app:

- **Auth Cop** — security reviews with the decision (approved / awaiting confirmation / declined)
- **Secret Safe** — redaction notices when secrets are detected in a message
- **Helping Hand** — suggestions when a run needs a nudge

_Last updated: July 2026_
