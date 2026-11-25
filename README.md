# Bipa plugins for Claude

This repository contains separate packages for personal and Business accounts.

| Plugin | Package | Guide |
| --- | --- | --- |
| Bipa | [`plugins/bipa`](plugins/bipa) | [Personal account setup](https://agents.bipa.app/docs/claude) |
| Bipa Business | [`plugins/bipa-business`](plugins/bipa-business) | [Business setup](https://agents.bipa.app/docs/business/claude-code) |

Submit each package folder separately to the Claude directory. The repository root is not an installable plugin: combining the packages makes the directory scan encounter nested plugin manifests.

The personal plugin uses `https://mcp.bipa.app/mcp`. Ordinary Pix, boleto and DDA requests need approval in Bipa; previously authorized trusted-contact Pix can execute immediately within the existing limits after explicit confirmation. See the [personal README](plugins/bipa/README.md) and [reviewer guide](plugins/bipa/REVIEWING.md) for permissions and the fictional test flow.
