# Dexmond Technologies — Claude Code plugins

Public marketplace for [Dexmond Technologies](https://dexmond.com) plugins for
Claude Code. The plugin code itself is distributed from PyPI; this repository
holds only the marketplace and plugin manifests.

## Install

In Claude Code:

```
/plugin marketplace add Dexmond-Technologies/claude-plugins
/plugin install dexmond-atlas@dexmond-technologies
```

Reload Claude Code when prompted.

### Prerequisite

The `dexmond-atlas` plugin runs its MCP server with [`uv`](https://docs.astral.sh/uv/)
(`uvx`). Install it once per machine:

```sh
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

## Plugins

### dexmond-atlas

Authorized infrastructure intelligence for Claude: map your estate, build a
**digital twin** of your company's infrastructure, run bounded discovery, and
surface automation opportunities. Read-only and human-approved.

On first use the plugin fetches [`dexmond-atlas`](https://pypi.org/project/dexmond-atlas/)
from PyPI and boots a local ATLAS instance on `127.0.0.1` — no hosting required.
It starts with **no scan scope** (nothing is scanned until you authorize a
network in the plugin's settings) and connects to a self-hosted ATLAS instead if
you provide a remote URL.

See the plugin's own documentation in
[`Dexmond-Technologies/agent-atlas`](https://github.com/Dexmond-Technologies/agent-atlas)
for configuration and the safety model.

## License

The `dexmond-atlas` plugin and the ATLAS software are proprietary
(© Dexmond Technologies Ltd). The manifests in this repository are published to
enable installation; they do not grant a license to the underlying software.
