# Commands

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

_Last updated: July 2026_
