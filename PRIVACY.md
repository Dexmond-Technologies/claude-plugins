# Privacy Policy — Dexmond ATLAS plugin for Claude

Last updated: 30 October 2026. Publisher: Dexmond Technologies Ltd, Ireland
(support@dexmond.com).

This policy covers the Dexmond ATLAS plugin (`dexmond-atlas`) and the ATLAS
software it runs. It does not cover dexmond.com, which has its own policy at
<https://dexmond.com/privacy.html>, or Claude itself, which Anthropic's terms
and privacy policy cover.

## What the plugin does with data

- **Runs on your computer.** By default the plugin starts ATLAS on
  `127.0.0.1` on your own machine and stores everything ATLAS records (its
  database, a generated access token and a server log) in the plugin's data
  folder on your machine (`~/.claude/plugins/data/dexmond-atlas-dexmond-technologies/atlas`).
- **Sends nothing to Dexmond.** ATLAS contains no telemetry, analytics or
  usage reporting. Dexmond receives no data from your use of the plugin.
- **Shares tool results with Claude.** When Claude calls an ATLAS tool, the
  result (for example your inventory or analysis results) becomes part of your
  Claude conversation and is handled under Anthropic's terms.

## Data collection

ATLAS records only what you give it or authorise it to collect:

- information about systems on networks **you explicitly authorise** in the
  plugin's settings (nothing is scanned until you do; unrestricted ranges are
  refused);
- data you import (for example company tables or the synthetic demo company);
- ATLAS's own records: an audit log of actions and a server log.

It may include personal data if your systems or imports contain it (for
example account names discovered from an identity system). You decide what
to authorise and import, and you are responsible for having the right to do so.

## Use and storage

The data is used only to answer your questions through ATLAS's tools. It is
stored unencrypted in the data folder above, protected by your operating
system's file permissions; use full-disk encryption on machines that hold
sensitive data.

## Third-party sharing

- **PyPI**: when the plugin starts, `uvx` downloads the published
  `dexmond-atlas` package from the Python Package Index. PyPI receives your IP
  address as for any download.
- **Networks you authorise**: ATLAS connects to them to collect evidence.
- **A remote ATLAS** (optional): if you set a Remote ATLAS URL and token, tool
  calls go to that server instead of a local one. That server's operator is
  responsible for its data.
- Nothing else. Dexmond does not sell or share your data.

## Data retention

Data stays on your machine until you delete it. To remove it, uninstall the
plugin and delete the data folder above. Dexmond keeps no copy.

## Your rights and contact

Because the data stays on your machine, you control it directly. For questions
about this policy or the plugin, contact support@dexmond.com. To report a
security issue, write to security@dexmond.com. If you are in the EU you may
complain to your data protection authority; in Ireland, the Data Protection
Commission (dataprotection.ie).
