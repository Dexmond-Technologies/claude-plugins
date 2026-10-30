# Dexmond ATLAS for Claude

ATLAS gives Claude a read-only view of the systems you authorise: an
inventory and dependency map (a digital twin) of your hosts, services,
databases and APIs, the impact of a failure, drift since the last snapshot,
workflow findings where people bridge systems by hand, and estimated
automation opportunities. It can also model a company (finances, capacity,
suppliers, processes) from data you import.

Claude gets read-only tools plus one action: starting a discovery of networks
you have authorised. Claude can never execute, approve or roll back a change;
inside ATLAS every change needs approval by a separate person.

## What the plugin runs

- **An MCP server, `atlas`**: `uvx --from dexmond-atlas[mcp]==1.2.0rc5
  atlas-mcp`, which downloads that exact published version from PyPI. It needs
  [`uv`](https://docs.astral.sh/uv/) on your machine.
- **A local ATLAS**: with no remote URL configured, the MCP server starts
  ATLAS on `127.0.0.1` with its data in the plugin's data folder, a generated
  access token, and **no authorised scan scope**.
- **Seven agents** (company research, finance, operations, process
  intelligence, reporting, security, supply chain) that answer from ATLAS's
  tools. They are read-only.

## What it connects to

PyPI (to download the package), the networks you authorise in the plugin's
settings, and — only if you configure it — a self-hosted ATLAS at the Remote
ATLAS URL. It sends nothing to Dexmond. See the [Privacy Policy](PRIVACY.md).

## Settings

- **Authorized scan scope**: comma-separated CIDRs ATLAS may discover, e.g.
  `192.168.1.0/24`. Empty means nothing is scanned. Only authorise networks
  you own or have permission to assess.
- **Remote ATLAS URL, token and workspace** (optional): connect to a
  self-hosted ATLAS instead of the local one. The token is stored as a
  sensitive setting.

## Try it with sample data

A fresh ATLAS is empty. To try the tools without real systems, load the
synthetic demo company (fictional, labelled "(demo)" everywhere) into the
plugin's local ATLAS:

```bash
uvx --from 'dexmond-atlas[mcp]==1.2.0rc5' atlas-demo
```

Remove it later by deleting the plugin's data folder.

## Example prompts

- "Use ATLAS to summarise Northwind Components' finances: which business unit has the better margin?"
- "Which suppliers does ATLAS know about, and which products depend on them?"
- "What would the margin of the Sensors unit be if its costs rose by 10%?"
- "List the systems ATLAS has discovered and how fresh the evidence for each is."
- "If the main database went down, what depends on it?"

## Privacy Policy

The plugin runs ATLAS on your machine, stores its data locally, and sends no
data to Dexmond. Tool results become part of your Claude conversation. Full
policy: [PRIVACY.md](PRIVACY.md) (published at
<https://github.com/Dexmond-Technologies/claude-plugins/blob/main/plugin/PRIVACY.md>).

## Support

support@dexmond.com · security issues: security@dexmond.com ·
<https://dexmond.com/agent-atlas.html>

## Licence

Proprietary software of Dexmond Technologies Ltd. Use of ATLAS is subject to
Dexmond's licence terms.
