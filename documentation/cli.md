---
icon: terminal
---

# WorkflowFiesta CLI

The WorkflowFiesta CLI brings AI-powered workflow automation directly to your terminal. Chat with agents, switch between them, and manage conversations — all without leaving the command line.

## Installation

{% tabs %}
{% tab title="Homebrew (macOS / Linux)" %}
```bash
brew install fiestatools/tap/workflowfiesta
```
{% endtab %}
{% tab title="curl (macOS / Linux)" %}
```bash
curl -fsSL https://workflowfiesta.com/install-cli | bash
```
{% endtab %}
{% tab title="Direct download" %}
Download the latest binary for your platform from the [GitHub releases page](https://github.com/fiestatools/workflowfiesta-cli/releases):

- **macOS** — `workflowfiesta-darwin-arm64` or `workflowfiesta-darwin-amd64`
- **Linux** — `workflowfiesta-linux-amd64`
- **Windows** — `workflowfiesta-windows-amd64.exe`

Make the binary executable and move it somewhere on your `$PATH`:

```bash
chmod +x workflowfiesta-darwin-arm64
mv workflowfiesta-darwin-arm64 /usr/local/bin/wf
```
{% endtab %}
{% endtabs %}

## Quick Start

```bash
# Start the CLI
wf

# Or use the full name
workflowfiesta
```

On first run you will be prompted to authenticate with your API token. You can generate one in the WorkflowFiesta web app under **Settings → API Keys**.

{% hint style="info" %}
Your token and preferences are stored locally in `~/.config/workflowfiesta/cli/`. Nothing is written to a system-wide location.
{% endhint %}

## Command Palette

Press `/` at any time to open the command palette.

| Command | Description |
|---------|-------------|
| `/new` | Start a new conversation |
| `/agent` | Switch to a different agent |
| `/rename <new title>` | Rename the current conversation |
| `/history` | Browse past conversations |
| `/settings` | Open the settings panel |
| `/copy` | Copy the last reply to clipboard |
| `/help` | Show help and keyboard shortcuts |

## Switching Agents

Run `/agent` to open the agent picker. It lists every agent in your org with its description. Selecting one switches the **current conversation** to that agent — it does not change your default.

To set a persistent default agent, open `/settings` and choose one under **Default agent**. Select **Use account default** to follow whatever your account has set in the web app.

## Conversation History

Run `/history` to browse previous conversations. Conversations are stored locally and synced with the backend.

| Key | Action |
|-----|--------|
| `Enter` | Reopen the selected conversation |
| `r` | Rename the selected conversation |
| `Space` | Mark / unmark for bulk delete |
| `d` | Delete selected (or marked) conversations — asks for confirmation |

## Settings Panel

Run `/settings` or press `Ctrl+S` to open the settings panel. It shows:

- **Account** — who you are signed in as, your organisation, and the active token with its expiry
- **Configuration** — API base URL and request timeout
- **Default agent** — the agent new conversations start with

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

## Development

```bash
# Install dependencies
bun install

# Run in development mode
bun dev

# Build for all platforms
bun run build
```

---

*Last updated: July 2026*