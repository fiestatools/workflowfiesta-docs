# Configuration

## Settings Panel

Run `/settings` or press `Ctrl+S` to open the settings panel. It shows:

- **Account** — who you are signed in as, your organisation, and the active token with its expiry
- **Configuration** — API base URL and request timeout
- **Default agent** — the agent new conversations start with

## Configuration Files

All config is stored in `~/.config/workflowfiesta/cli/`.

| File | Purpose |
|------|---------|
| `config.json` | User preferences (default agent, timeout, API URL) |
| `credentials.json` | Auth token and API base URL |
| `conversations.json` | Local conversation index |

{% hint style="warning" %}
Do not edit `credentials.json` by hand. Re-authenticate by running `wf` and following the login prompt, or by updating the token in `/settings`.
{% endhint %}

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `/` | Open command palette |
| `Ctrl+B` | Toggle side panel |
| `Ctrl+S` | Toggle settings |
| `Ctrl+N` | New conversation |
| `Shift+Enter` | Insert a newline in the input |
| `Enter` | Send message |
| `Ctrl+C` | Quit |

_Last updated: July 2026_
