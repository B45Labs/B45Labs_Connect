## Changelog
All notable changes to this project will be documented in this file.

This project adheres to [Semantic Versioning](https://semver.org/) and follows the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) standard.

---

## [0.0.1] – 2026-11-15

> B45 Labs | Connect puts an AI assistant inside Revit and opens your model to the AI tools
> you already use. First release.

### Added

- Chat about the open model, inside Revit. A dockable B45 Labs | Connect pane with a chat that
  reads the active document through the B45 Labs tools: warnings, views, rooms, levels, links,
  clashes, model health and more. The Stop button cancels the current answer and the chat stays
  ready for the next question.
- Bring your own AI account. It works with an Anthropic (Claude) or an OpenAI API key from the
  provider's developer console; a Claude.ai or ChatGPT subscription does not work here. The key
  is stored encrypted for your Windows user on your computer, and the chat sends its requests
  straight to Anthropic or OpenAI.
- Nothing changes in your model without your say-so. Every action that writes to the model, such
  as delete, rename, set a parameter or create sheets, stops at a confirmation card. Allow runs
  it; Deny, or no answer, leaves the model untouched.
- Launch ribbon commands from the chat. Ask for a command by name and the Assistant opens its
  window as a ribbon click would: it opens the command, you run it.
- Ask how a command works. The Assistant explains any B45 Labs command from an offline copy of
  the documentation and gives you the link to the full page.
- Dictate instead of typing. Voice dictation in Portuguese and English through your OpenAI key,
  with a live level meter and automatic send when you stop talking. Without an OpenAI key,
  Windows speech recognition takes over (not available in Portuguese).
- An MCP server for your other AI clients. "Enable in Claude Desktop" registers Connect in one
  click and Claude Desktop can read your open model after a restart; "Copy Claude Code command"
  gives you the single line to paste; other local MCP clients can point at the same executable
  with a hand-written configuration entry.
- Reading from outside, with limits. External clients get 58 tools: 47 that read, check and audit the
  model and 11 that only change what you are looking at (open or isolate a view, select
  elements, section box, reference points, colored walls, refresh the Library pane, open a B45
  Labs command or a Revit dialog and close it again). Every change to the model itself stays
  inside Revit behind the confirmation card. The bridge between the client and Revit runs on
  your computer over a local named pipe.

### Notes

- An add-on for B45 Labs | Coordination 3.0 or newer: the Connect button lives on the
  Coordination tab, and the tools the Assistant and the MCP server run are Coordination's (and
  Library's, when Library is installed). Full support: Revit 2023, 2024, 2025, 2026 and 2027,
  on Windows 10 and 11.
- Known limits: one Revit instance at a time, the active document only, and one external MCP
  client at a time.
- Connect sends short reports tied to a random install ID (failure reports, usage counts and one installation
  record) to B45 Labs, and they stop when you turn off Share usage data in
  Coordination. It never sends your prompts, the AI's answers or anything from your model. See
  [PRIVACY.md](PRIVACY.md).
