# B45 Labs – Support

**Last updated:** 2026-11-14  
**Applies to:** B45 Labs | Connect 1.0.0 (Revit 2023, 2024, 2025, 2026, 2027), an add-on that requires B45 Labs | Coordination 2.2 or newer

## 1. Support channels
- Email: **support@B45Labs.com**
- Documentation: the Connect guides on b45labs.com (Docs > B45 Connect), including a troubleshooting page for the bracketed error codes (`[RevitNotAvailable]`, `[BridgeBusy]`, `[ContractMismatch]`).

## 2. Before you write: three quick checks
1. **B45 Labs | Coordination 2.2 or newer is installed.** The Connect button lives on the Coordination tab; without Coordination there is no button and no tools.
2. **Only one external MCP client is connected.** Claude Desktop keeps the Connect server alive in the background after its window is closed (quit it from the system tray); each open Claude Code session keeps one alive too. A second client is told `[BridgeBusy]`.
3. **The client points at the installed executable**, `%AppData%\Autodesk\Revit\Addins\<RevitVersion>\B45Labs\Connect\mcp\B45Labs.Connect.exe`, the path shown in the Connect pane under **Server (.exe) path**.

## 3. What to include in a support request
To help us reproduce and fix issues quickly, include:
- B45 Labs | Connect version (the **Add-in** row in the pane's Setup tab) and the output of `B45Labs.Connect.exe --version`
- B45 Labs | Coordination version
- Revit version (2023, 2024, 2025, 2026, or 2027) + build number if available
- Which part is affected: the Connect pane / Assistant (and the provider: Anthropic or OpenAI), voice dictation, or the MCP server / an external client
- Your MCP client and its version, if the issue is with an external client (Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI, ChatGPT through the tunnel, other)
- The output of `B45Labs.Connect.exe --selftest` (run from the `mcp` folder in PowerShell with Revit open; exit codes: 0 OK, 2 RevitNotAvailable, 3 BridgeBusy, 4 ContractMismatch)
- The last lines of `%AppData%\B45Labs\Connect\mcp_server.log` (tool names and timings only; it never contains model data)
- A short description of what you were doing
- Steps to reproduce (if you can)
- Screenshot of the message/output
- Error timestamp (approximate) if applicable

## 4. Privacy note
Please **do not** send:
- full file paths,
- proprietary model files,
- client confidential information,
- your AI provider API keys or any secrets.

If a screenshot includes file paths, API keys, or sensitive details, please redact them before sending.

## 5. Support scope
Support is provided on a **best-effort** basis unless you have a separate written support agreement with B45 Labs.

Issues that originate with a third-party AI provider (Anthropic, OpenAI) or a third-party AI client (Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI, ChatGPT and OpenAI's tunnel service), including provider availability, model behaviour and answers, billing, plan rules, or their account and API-key management, are outside B45 Labs' control; please contact the respective provider for those.
