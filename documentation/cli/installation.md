# Installation

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

## First run

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

_Last updated: July 2026_
