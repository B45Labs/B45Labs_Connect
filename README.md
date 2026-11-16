# B45 Labs | Connect: Revit Add-in and MCP Server

![Revit](https://img.shields.io/badge/Revit-2023--2027-0696D7?style=flat-square&logo=autodesk&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square)
![License](https://img.shields.io/badge/License-Proprietary-red?style=flat-square)

> B45 Labs | Connect puts an AI assistant inside Autodesk Revit and opens your open model to the AI tools you already use: Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI and other MCP clients.

> **Part of the B45 Labs suite.** Connect is an add-on to **B45 Labs | Coordination 3.0 or newer**. Coordination brings the tools; Connect brings the chat, the voice and the bridge. The Connect button lives on the Coordination tab in Revit.

---

## Where to get it

This repository holds the public documentation and releases of B45 Labs | Connect. There is no release here yet. The installer and the Claude Desktop extension (`B45Labs.Connect.mcpb`) arrive with the first GitHub Release on the [**Releases**](https://github.com/B45Labs/B45Labs_Connect/releases) page. Until then, see [b45labs.com/download](https://b45labs.com/download).

---

## Who it is for

BIM coordinators, modelers and managers who work in Revit and want to ask about the open model in plain language, from inside Revit or from the AI client they already use, with every change to the model staying behind a confirmation.

---

## Key Features

- **Chat about the open model, inside Revit.** A dockable "B45 Labs | Connect" pane with a chat that reads the active document through the B45 Labs tools: warnings, views, rooms, levels, links, clashes, model health and more.
- **Your own AI account.** Works with an Anthropic (Claude) or an OpenAI API key from the provider's developer console, billed per token to you. A Claude.ai or ChatGPT subscription is not an API key and does not work here. The key is stored encrypted on your computer, and the chat sends its requests straight to the provider.
- **Every change asks first.** Every action that writes to the model stops at a confirmation card. **Allow** runs it; **Deny**, or no answer, leaves the model untouched.
- **Launch commands and get help from the chat.** Ask for a B45 Labs command by name and the Assistant opens its window as a ribbon click would. Ask how a command works and it explains it from an offline copy of the documentation.
- **Voice dictation.** Dictate in Portuguese and English through your OpenAI key. Without an OpenAI key, Windows speech recognition takes over (not available in Portuguese).
- **An MCP server for your AI clients.** "Enable in Claude Desktop" registers Connect in one click; the pane gives each other client what it needs (a command, a config or a deeplink). Nothing goes through B45 Labs servers.
- **Non-destructive from the outside.** External AI clients get 58 tools: 47 that read, check and audit the model and 11 that only change what you are looking at. Every change to the model itself stays inside Revit behind the confirmation card.
- **ChatGPT for advanced users.** ChatGPT can reach the same local tools through OpenAI's Secure MCP Tunnel. The plan rules are OpenAI's.

---

## Requirements

| Requirement | Details |
|---|---|
| B45 Labs \| Coordination | 3.0 or newer (B45 Labs \| Library is optional; when installed, its tools are available to the Assistant too) |
| Autodesk Revit | 2023, 2024, 2025, 2026, 2027 *(full support)* |
| Operating System | Windows 10 / Windows 11 |
| Installation | Per-user, no administrator rights required |
| In-Revit Assistant and dictation | Your own Anthropic or OpenAI API key |
| External AI clients | An MCP-capable client; it uses its own account, so Connect needs no API key for this path |

---

## Installation

1. Install **B45 Labs | Coordination 3.0 or newer** first ([b45labs.com/download](https://b45labs.com/download)).
2. Download the Connect installer from [**Releases**](https://github.com/B45Labs/B45Labs_Connect/releases) once the first release is published.
3. Close Revit before installing.
4. Run the installer, accept the license, and select the Revit versions to install for. It stops with a clear message if Coordination 3.0 or newer is missing.
5. Launch Revit: the **Connect** button appears on the **B45 Labs | Coordination** tab and opens the Connect pane.
6. In the pane's Setup tab, paste your API key and click **Test key**, or pick your AI client and follow the buttons.

---

## Updates

New versions are published on the GitHub **Releases** page. Install the newer version over the current one; the installer updates the add-in and the MCP server together.

---

## Data and privacy

B45 Labs does not collect your conversations, your prompts, your voice, your model data or any file name or path. Connect sends B45 Labs only short reports tied to a random install ID: failure reports (the exception type and code, never a message), usage counts, and one installation record with a coarse region (continent, country and region, never a city or an IP). They follow the **Share usage data** switch in B45 Labs | Coordination: turn it off and Connect stops sending.

When you use the Assistant or voice dictation, your prompts and the model data the tools read go straight from your computer to the provider you chose (Anthropic or OpenAI) under your own key, and are processed under that provider's policies. External MCP clients forward tool results to their own provider under your account with that client. Nothing on these paths goes through a B45 Labs server. See [PRIVACY.md](PRIVACY.md) for every item.

---

## Known limits

- One Revit instance at a time: the first Revit session owns the connection.
- Works on the active document only.
- One external MCP client at a time.
- The interface is in English; the Assistant answers in your language.

---

## Important: verification responsibility

Connect is a productivity aid, not a substitute for professional judgment. AI-generated answers and any action taken through the Assistant or an MCP client must be independently reviewed and validated by you before use in any project deliverable. See [TERMS.md](TERMS.md), Section 8.1.

---

## Documentation

| Document | Description |
|---|---|
| [b45labs.com/connect](https://b45labs.com/connect) | Product page |
| [Connect guides](https://b45labs.com/docs/connect-claude-desktop) | Setup and usage guides on b45labs.com |
| [TERMS.md](TERMS.md) | Terms of Use / EULA |
| [PRIVACY.md](PRIVACY.md) | Privacy Policy |
| [CHANGELOG.md](CHANGELOG.md) | Version history |
| [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) | Third-party licenses |
| [SUPPORT.md](SUPPORT.md) | Support information |
| [SECURITY.md](SECURITY.md) | Security policy |
| [LICENSE](LICENSE) and [LICENSE_PROPRIETARY.md](LICENSE_PROPRIETARY.md) | Proprietary license |

---

## Support

Email: **support@b45labs.com**, or open an issue at [github.com/B45Labs/B45Labs_Connect/issues](https://github.com/B45Labs/B45Labs_Connect/issues).

When reporting issues, include: B45 Labs | Connect and Coordination versions, Revit version and build number, your AI client or provider and its version, the output of `B45Labs.Connect.exe --selftest`, steps to reproduce, a timestamp and a screenshot (redact sensitive details). Never send API keys. See [SUPPORT.md](SUPPORT.md).

---

## Copyright

Copyright (c) 2026 B45 Labs. All rights reserved.
Use of this Software is governed by [TERMS.md](TERMS.md).
