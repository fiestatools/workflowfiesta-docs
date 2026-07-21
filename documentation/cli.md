---
icon: terminal
---

# CLI

The WorkflowFiesta CLI lets you interact with the platform from your terminal — trigger workflows, manage agents, and run scripts without opening the browser.

{% hint style="info" %}
The CLI runs on top of the **Runner**. You need a connected runner before the CLI can execute commands on your machine. See [Runner](runner.md) to get set up first.
{% endhint %}

## Installation

{% tabs %}
{% tab title="macOS" %}
```bash
curl -L https://github.com/ss-libs/workflowfiesta-runner/releases/latest/download/workflowfiesta-runner-linux-amd64 -o wf
chmod +x wf
sudo mv wf /usr/local/bin/wf
```

Or download the GUI desktop app from the [releases page](https://github.com/ss-libs/workflowfiesta-runner/releases/latest).
{% endtab %}

{% tab title="Linux" %}
```bash
curl -L https://github.com/ss-libs/workflowfiesta-runner/releases/latest/download/workflowfiesta-runner-linux-amd64 -o wf
chmod +x wf
sudo mv wf /usr/local/bin/wf
```

For headless / server installs, use the binary directly without moving it to `/usr/local/bin`.
{% endtab %}

{% tab title="Windows" %}
Download the `.exe` from the [releases page](https://github.com/ss-libs/workflowfiesta-runner/releases/latest) and add it to your `PATH`, or run it from the directory where you saved it.

```powershell
.\workflowfiesta-runner-windows-amd64.exe --code YOUR_REGISTRATION_CODE
```
{% endtab %}
{% endtabs %}

## Authentication

Connect the CLI to your WorkflowFiesta organization using a registration code. Ask the agent to generate one:

> "Generate a runner registration code called my-laptop."

Then paste the code:

```bash
wf --code YOUR_REGISTRATION_CODE
```

The code is a one-time token. Once used, the runner is registered and stays connected until you remove it.

{% hint style="warning" %}
Registration codes expire after **60 minutes** by default. If yours has expired, ask the agent to generate a new one.
{% endhint %}

## Core Commands

### Trigger a workflow

```bash
wf workflow trigger "My Workflow Name"
```

Pass input as JSON:

```bash
wf workflow trigger "Send Weekly Report" --input '{"recipient": "team@example.com"}'
```

### List workflows

```bash
wf workflow list
```

### Run a bash script via the agent

```bash
wf run bash "ls -la ~/Documents"
```

### Check runner status

```bash
wf status
```

### View recent runs

```bash
wf runs list --limit 10
```

## Using with Workflows

The CLI is most useful when combined with scheduled or event-driven workflows. A common pattern is triggering a workflow from a CI/CD pipeline or a cron job on your machine:

```bash
# In a cron job or CI step
wf workflow trigger "Nightly Data Sync" --input '{"date": "2026-07-21"}'
```

The workflow runs on the platform, uses your connected runner for any local steps, and you get the result in your WorkflowFiesta chat.

## Environment Variables

You can set your registration code as an environment variable instead of passing it each time:

```bash
export WF_CODE=YOUR_REGISTRATION_CODE
wf status
```

## Updating the CLI

The CLI binary self-updates. To check your current version:

```bash
wf --version
```

To update to the latest release, re-run the installation command for your platform. The latest release is always at the [releases page](https://github.com/ss-libs/workflowfiesta-runner/releases/latest).

{% hint style="success" %}
**Current stable release:** v0.11.5
{% endhint %}

## Troubleshooting

<details>

<summary>Command not found: wf</summary>

The binary isn't on your `PATH`. Either move it to `/usr/local/bin/` (macOS/Linux) or run it with the full path: `./wf --code YOUR_CODE`.

</details>

<details>

<summary>Registration code expired</summary>

Codes expire after 60 minutes. Ask the agent: "Generate a new runner registration code." The old code is automatically revoked.

</details>

<details>

<summary>Runner shows as offline after connecting</summary>

Keep the CLI process running — it needs to stay active to maintain the connection. For persistent background connections, use the GUI desktop app or run the binary as a system service.

</details>

<details>

<summary>Workflow trigger returns an error</summary>

Check that the workflow name matches exactly (case-sensitive). Use `wf workflow list` to see the exact names of your workflows.

</details>

---

*Last updated: July 2026*
