# B45 Labs: Security Policy

**Last updated:** 2026-11-13 (data flows corrected to match what the Software sends to B45 Labs; chat history and queue files listed). Earlier, 2026-10-04 (WP-C74 refresh: data inventory, local storage locations, diagnostics that are safe to share)  
**Applies to:** B45 Labs | Connect 0.0.1 (Revit 2023, 2024, 2025, 2026, 2027), an add-on that requires B45 Labs | Coordination 3.0 or newer

## Reporting a vulnerability
If you believe you have found a security vulnerability in B45 Labs | Connect, please report it responsibly:

- Email: **support@B45Labs.com**
- Subject: **Security Vulnerability Report**

Please include:
- a clear description of the issue,
- steps to reproduce,
- the affected version(s) (`B45Labs.Connect.exe --version` prints the MCP server's version and contract; the Connect pane's Setup tab shows the add-in version),
- any proof-of-concept details (if safe to share).

Please do **not** include your AI provider API keys or other secrets in a report.

We will acknowledge receipt and work to validate and address the issue as appropriate.

## What the Software stores, and where
- **AI provider API keys** (Anthropic, OpenAI): `%LocalAppData%\B45Labs\Connect\`, one file per provider, encrypted with Windows DPAPI for the current Windows user with per-provider entropy. Another Windows account or another machine cannot decrypt them. Deleted by **Clear** (per provider) or **Forget all keys on this PC**.
- **MCP server log**: `%AppData%\B45Labs\Connect\mcp_server.log`, rotated once to `mcp_server.1.log` at 1 MB. Lines carry a timestamp, the tool name, the outcome and the elapsed time; never tool arguments or results.
- **Add-in error log**: `%AppData%\B45Labs\Connect\connect_errorlog.jsonl`, sanitised before writing (file paths, model names, e-mail addresses redacted).
- **Chat history**: `%LocalAppData%\B45Labs\Connect\history\`, your conversations as you saw them, kept on this PC and never sent to B45 Labs. A chat can include names and numbers from your models, and the files are not password protected.
- **Failure and usage queues**: `%LocalAppData%\B45Labs\Connect\failure_queue.jsonl` and `usage_queue.jsonl`, the short reports waiting to be sent (no message text, no content); nothing is written to them while the usage switch is off.
- **Claude Desktop configuration**: the Software writes a `b45-connect` entry to `%AppData%\Claude\claude_desktop_config.json` only when you click **Enable in Claude Desktop**, and removes it on **Disable**. It edits no other third-party configuration file.

## Data flows, in one paragraph
The Software sends B45 Labs four kinds of small reports tied to a random install ID, and nothing else apart from the update check (`PRIVACY.md` section 4): failure reports (exception type and code, never a message), usage counts, one installation record and the coarse region inside it (continent, country and state or province, looked up from your IP address by ipwhois.app; the IP address is not part of the records B45 Labs keeps, see `PRIVACY.md` section 3.5). It never sends your conversations, your model data or any file name or path, and all four follow the **Share usage data** switch in B45 Labs | Coordination (`PRIVACY.md` sections 1 and 2). The in-Revit Assistant sends your prompts and the model data its tools read (counts, ids, findings, names, parameter values and schedule rows; never full file paths, Windows user names or geometry) to the AI provider **you** chose, with **your** key, over the provider's HTTPS connection. Voice dictation uploads the recorded audio to OpenAI with your OpenAI key. External MCP clients receive tool results over a **local named pipe** on your computer and forward them to their own provider under your account with that client; the pipe is not exposed on the network and serves one client at a time. External clients get 58 tools (47 reading, checking and audit tools and 11 that only change what you are looking at); every tool that writes to the model exists only inside Revit, behind a confirmation card, and is never advertised to an external client. The optional ChatGPT path routes that same tool traffic through OpenAI's Secure MCP Tunnel, inside your own OpenAI organisation. See `PRIVACY.md` section 12.

## Diagnostics that are safe to share
- `B45Labs.Connect.exe --version` and `B45Labs.Connect.exe --selftest` (from the `mcp` folder of the Connect install) print versions, contract compatibility, the active document title and the tool count; no model content.
- The tail of `mcp_server.log` contains tool names and timings only.

Redact the document title if it is confidential. Never share an API key.
