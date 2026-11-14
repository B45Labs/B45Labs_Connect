# B45 Labs – Privacy Policy

**Effective date:** 2026-01-01  
**Last updated:** 2026-11-13 (corrected to match what the Software does: it also sends short failure reports, and this text no longer says that nothing is transmitted, that error data is not collected or that no region is sent: sections 1, 2, 3, 4, 5, 6, 8 and 9 and the local files; the local chat history is now listed). Earlier, 2026-11-01 (the Software also sends one installation record with a coarse location: sections 1, 2.3, 2.5 and local files). Earlier, 2026-10-31 (the Software now sends anonymous usage counts to B45 Labs: sections 1, 2, 4, 5, 6, 8 and 9). Earlier, 2026-10-25 (spec crosscheck: the tools now also read parameter values and schedule rows, section 3 and 12; the tool count is stated again). Earlier, 2026-10-04 (WP-C74 refresh: two AI providers, dictation audio, the embedded documentation index, the local named pipe, the optional ChatGPT tunnel, the local log files, and the statement that the 2026-10-04 build collected no usage telemetry)  
**Applies to:** B45 Labs | Connect 1.0.0 (Revit 2023, 2024, 2025, 2026, 2027), an add-on that requires B45 Labs | Coordination 2.2 or newer

This Privacy Policy explains how B45 Labs (“B45 Labs”, “we”, “our”, “us”) handles information when you use the B45 Labs | Connect Revit add-in and its companion MCP server (the “Software”).

## 1. Scope
This Policy applies to information handled by the Software: what stays on your computer, what the Software sends to third parties on your instruction, and what, if anything, reaches B45 Labs.

**In short.** We do not collect your conversations, your prompts, your voice, your model data or any file name or path. We collect errors, to fix and improve the product, and, under the same switch, anonymous usage counts, one installation record per installation and a coarse region (continent, country and region, never a city). None of these reports carries a person's name, an e-mail address, a file name or a folder path.

**In this build, the Software sends four kinds of small, anonymous reports to B45 Labs:** failure reports (that something in Connect failed, with the exception type and code, never a message), usage counts (that a feature was used: for example the pane was opened, a chat message was sent, a tool ran), one installation record (section 2.3) and the coarse region inside it (section 2.5). It never sends what you typed, what the AI answered, or what is in your model. All four follow the same opt-out as B45 Labs | Coordination: the **Share anonymous usage data** switch in Coordination turns them off. It has no profile window. Section 2 states what is collected, category by category.

**Important: AI providers are separate.** B45 Labs | Connect lets you use an in-Revit AI Assistant and a local MCP Bridge that work with **third-party AI providers and AI clients**. The Assistant uses the provider **you** choose, **Anthropic** or **OpenAI**, through **your own** API key. External MCP clients (such as Claude Desktop) use their own account with their own provider. When you use those features, your prompts and the model data the tools read are sent to that provider or client and are processed under **their** privacy policies and terms, not this one. Section 12 describes each path in detail.

**Coordination is separate too.** The Software requires B45 Labs | Coordination, which has its own Privacy Policy covering its own telemetry and settings. Nothing in this Policy changes what Coordination does, and nothing Coordination collects is attributed to Connect.

## 2. What We Collect

**Status of this build (2026-11-13): the Software collects the usage counts described in 2.1, the failure reports in 2.2, the installation record in 2.3 with the identifiers of 2.4 and the coarse region of 2.5, and nothing in the other categories.** It is on by default and stops when you turn off **Share anonymous usage data** in B45 Labs | Coordination (section 8). Sections 2.1 to 2.6 define the ceiling: a future release that collects more will say so in its release notes, and this section will gain a dated paragraph saying exactly what was added and how to turn it off. The Software will never start collecting silently.

### 2.1 Usage Data
*Collected in this build, as counts.* Each count is the name of something that happened, with how many times and whether it succeeded:
- the add-in started in a Revit session;
- the Connect pane was opened (at most once per half hour);
- a chat message was sent, with the AI provider used (Anthropic or OpenAI), never the message;
- a prompt was picked from the prompt library: a prompt that ships with the Software is counted by its fixed name; a prompt you wrote is counted only as “custom”, with no text and no name;
- a tool ran, with the tool's name (only names from the Software's own fixed list), whether it was started from the in-Revit chat or by an external AI client, and whether it succeeded;
- which kind of external AI client connected (Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI, or Other), once per Revit session.

Counts are grouped per session before they are sent, together with the add-in version, the Revit version and build, and the Revit interface language. **Never** the content of a prompt, an answer, a tool argument or a tool result, never a model, project or file name, and never an API key.

### 2.2 Error and Diagnostic Data
*Collected, as short failure reports.* When Connect catches a failure in its own code and keeps running, or an unhandled exception passes through at least one frame of Connect's own code, it queues one short report. Failures of other add-ins are not reported, and repeats of the same failure are throttled. A report carries the installation identifier of 2.4, the Revit name, version and build, the Connect version, a timestamp, a command name made of two cleaned code identifiers (for example `ConnectHandled.ConnectProcess.UnhandledException`), a fixed sentence holding the exception type and its code, and a fixed text in place of a stack trace. It carries **no message text**, no prompt, no answer, no model, project or file name, no path and no e-mail address: the Software reads only the exception type and code. Reports wait in `%LocalAppData%\B45Labs\Connect\failure_queue.jsonl` until they are sent and are dropped after 3 days. Nothing is written when you have turned **Share anonymous usage data** off in Coordination. The **local** error log (section 2, “What the Software stores on your computer”) is separate: it keeps a sanitised message for support on your computer and is never transmitted.

### 2.3 Installation and Update Data
*Collected, as one record per installation and Revit version.* The first time Connect runs, and again only when the Connect version or the Revit interface language changes, it sends: the Connect version first installed and the one running now, the version it was upgraded from, the dates it was first seen and last updated, the Revit name, version and build, and the Revit interface language, together with the installation identifier of 2.4. It also carries your **coarse location** (continent, country and region, never a city), described in 2.5. Connect keeps what it last sent in `%LocalAppData%\B45Labs\Connect\installation_sent.json` so that it does not send the same record again. It follows the same opt-out as the usage counts.

### 2.4 Pseudonymous Identifiers
*Collected.* Each count and each failure report carries the random installation identifier that B45 Labs | Coordination already created on this computer, and a random session identifier created each time Revit starts. Neither contains a name, an e-mail address or any other personally identifiable information. Connect creates no identifier of its own. It does not read the identifier until the file exists, so nothing is sent before Coordination has run once.

### 2.5 Region Data
*Collected, only inside the installation record of 2.3.* When that record is about to be sent, Connect asks a public IP-lookup service (**ipwhois.app**, the same one B45 Labs | Coordination and B45 Labs | Library use) where your internet connection is, and keeps only the **continent, country and region** it answers. The request goes from your computer to that service, which sees your IP address as any website you visit does. **B45 Labs never receives, stores or sends your IP address and never reads or stores a city.** The lookup follows the same opt-out as the usage counts: when you turn it off, it is not made. If the lookup fails, the record carries "Unknown" for these three fields and Connect tries once more later in the session.

### 2.6 User Profile Data (Voluntary)
*Not collected in this build.* The Software has no user-profile window and syncs no profile.

**What the Software stores on your computer (the usage queue and the failure queue are sent as described in 2.1 and 2.2; everything else below is never transmitted to B45 Labs):**

- **Your AI provider API keys**, one encrypted file per provider under `%LocalAppData%\B45Labs\Connect\`, protected with Windows DPAPI for your Windows user account (section 11).
- **Your microphone preference** for voice dictation, remembered on this PC.
- **The MCP server log**, `%AppData%\B45Labs\Connect\mcp_server.log` (rotated once to `mcp_server.1.log` at 1 MB). Each line carries a timestamp, the tool name, the outcome and the elapsed time; **never** the arguments sent or the results returned, so no model data lands in it.
- **The add-in error log**, `%AppData%\B45Labs\Connect\connect_errorlog.jsonl`, sanitised (file paths, model names and e-mail addresses are redacted when written).
- **The installation memory**, `%LocalAppData%\B45Labs\Connect\installation_sent.json`: what Connect last sent in its installation record (versions, dates, language, the installation identifier). It holds no content and is never sent as a file.
- **The usage queue**, `%LocalAppData%\B45Labs\Connect\usage_queue.jsonl`: the counts waiting to be sent (one short line per event, no content). It is emptied after each successful send, capped at 256 KB, and nothing is written to it while the usage switch is off.
- **The failure queue**, `%LocalAppData%\B45Labs\Connect\failure_queue.jsonl`: the short failure reports of 2.2 waiting to be sent (no message text and no content). Reports older than 3 days are dropped, and nothing is written to it while the usage switch is off.
- **Your chat history**, `%LocalAppData%\B45Labs\Connect\history\`: your conversations with the Assistant (what you saw in the chat: your messages, the answers and the tool and error lines), kept on this PC so that "New chat" does not throw the previous one away. A chat can include names and numbers from your models, and the files are not protected with a password. They are never sent to B45 Labs; delete the folder, or the chats you do not want, at any time.
- **An entry in Claude Desktop's configuration file** (`%AppData%\Claude\claude_desktop_config.json`) only when you click “Enable in Claude Desktop”; “Disable” removes it. The Software edits no other third-party configuration file.
- **The embedded documentation index**: an offline copy of the B45 Labs command documentation shipped inside the add-in, which the Assistant reads locally to explain a command. It makes no network request.

You can delete the log files at any time; they are recreated on the next run. Uninstalling removes the add-in and the MCP server; the key files and logs listed above may remain under your user folders and can be deleted by hand.

## 3. What We Do NOT Collect
We do not intentionally collect any “sensitive personal data” (special categories), such as health data, biometric identifiers, precise location data, government IDs, financial account data, or authentication credentials.

B45 Labs does not collect your conversations or your model data. The only things this build sends to B45 Labs are the reports of section 2 (failure reports, usage counts, the installation record and its coarse region). In particular, B45 Labs never receives:
- Project file contents, drawings, geometry, or BIM data.
- Revit model or family file names, file paths, or folder locations.
- The content of your Assistant prompts, conversations, or voice dictation (see section 12: that content goes to the AI provider you configured, not to B45 Labs).
- The tool results the Assistant or an MCP client reads from your model (counts, ids, findings, names, parameter values, schedule cell text, and the differences found when a specification table you provide is compared with the model). They go to the provider or client you chose, never to B45 Labs.
- Your AI provider API keys (see section 11).
- Payment information. Donations/support (if offered) are processed by third-party providers; B45 Labs does not receive or store payment details.
- Precise geolocation (street address / GPS coordinates), a city, or your IP address. The only location we receive is the coarse region of section 2.5: continent, country and region.
- Passwords, authentication credentials, or personal communications.
- Your Revit or Windows username.
- Device or hardware specifications (processor, memory, screen resolution) or operating-system details.

If such information appears in a user-provided support screenshot or log, please redact it before sharing.

## 4. How We Use Information

B45 Labs uses the failure reports, usage counts and installation records described in section 2 strictly for internal purposes:
- Measuring feature adoption and tool usage to prioritize development and improvements.
- Improving stability, performance, and reliability across different Revit versions and environments.
- Debugging and fixing errors and regressions.
- Validating installer/update distribution health (e.g., adoption by version, compatibility signals).
- Producing aggregated, anonymized metrics for roadmap planning.

## 5. Sharing and Disclosure
We do not sell your data and we do not share collected data with third parties for advertising or marketing.

The failure reports, usage counts and installation records are stored with the same hosting and database service that stores B45 Labs | Coordination's telemetry, used only to support our internal operations and not authorized to use the information for its own purposes.

We may disclose information if required by law, court order, or to protect our rights and the security of the Software.

## 6. Data Retention
Failure reports, usage counts and installation records are retained for up to **24 months** unless a longer retention is required to investigate recurring issues or to comply with legal obligations.

Local files on your computer are retained until you remove them:
- API keys: until you click **Clear** for a provider or **Forget all keys on this PC**.
- `mcp_server.log`: 1 MB, rotated once to `mcp_server.1.log`; two files is the whole retention. Delete them at any time.
- `connect_errorlog.jsonl`: until you delete it.
- `usage_queue.jsonl`: until the counts in it have been sent (or you opt out), and never more than 256 KB.
- `failure_queue.jsonl`: until the reports in it have been sent (or you opt out), and never longer than 3 days per report.
- `history\` (your chats): until you delete them, with the number of chats kept set in the History window (the older ones are removed first, favorites are kept).
- `installation_sent.json`: until you delete it. Deleting it only makes Connect send its installation record once more.


## 7. Security
Your API keys are encrypted at rest with Windows DPAPI for your Windows user account, one file per provider with its own entropy, so another Windows account or another machine cannot decrypt them. Requests to AI providers travel over the provider's own encrypted (HTTPS/TLS) connection directly from your machine. The MCP Bridge runs over a **local named pipe** on your computer and serves one external client at a time; it is not exposed on the network. The local log files never contain tool arguments or tool results. We implement reasonable administrative, technical, and organizational safeguards; however, no method of transmission or storage is 100% secure.

## 8. Your Choices and Requests
Connect has no usage switch of its own: it reads the one in B45 Labs | Coordination. The controls you have are there, in the Connect pane's **Setup** tab, and on your computer:
- **Share anonymous usage data** (in Coordination): turn it off and Connect stops counting, stops sending failure reports and installation records, and empties its queues. The change reaches Connect within about a minute.
- **Erase my data** (in Coordination): sends a deletion request to our server for the data tied to your installation identifier and deletes the B45 Labs data that Coordination stores on your PC. The files that Connect keeps (listed above) can also be deleted by hand.
- **Clear** (per provider) and **Forget all keys on this PC**: delete your saved API keys.
- **Microphone**: choose the recording device, or leave System default.
- **Disable** (Claude Desktop): removes the `b45-connect` entry the Software wrote to Claude Desktop's configuration.
- **Delete the log files** under `%AppData%\B45Labs\Connect\` at any time.
- **Uninstall**: removes the add-in and the MCP server.

You may also contact us to request information about data associated with your usage, or correction or deletion where applicable. We may ask for additional information to verify your request.

## 9. International Use
The Software may be used in different countries. B45 Labs processes the failure reports, usage counts and installation records on its backend, as described in B45 Labs | Coordination's policy. The AI providers and AI clients you choose process your prompts and model data where they operate, under their own policies (section 12).

## 10. Changes to This Policy
We may update this Policy from time to time. The “Last updated” date will reflect the most recent revision. Material changes, including the introduction of any telemetry, will be communicated through release notes and will appear here as a dated paragraph in section 2 before the collection starts.

## 11. AI Provider API Keys
The in-Revit Assistant and voice dictation require **your own** API key from an AI provider: **Anthropic** (console.anthropic.com) or **OpenAI** (platform.openai.com). These are pay-per-token developer keys; a Claude.ai or ChatGPT subscription is not an API key and does not work here. When you enter a key, it is stored **locally** on your computer, encrypted with Windows DPAPI for your Windows user, one file per provider, for the Software to use when it calls the provider on your behalf. **B45 Labs does not collect, receive, transmit to our servers, or store your API keys**, and never writes them to a log. The **Test key** button sends one request to the provider's models list to validate the key; nothing from your model is sent. **Clear** deletes one provider's key; **Forget all keys on this PC** deletes them all. Keep your keys confidential; you are responsible for their security and for any usage associated with them (see TERMS.md).

## 12. Data Sent to Third-Party AI Providers and AI Clients
The Software sends data to a third party **only when you actively use** the relevant feature, and only to the party you configured. Specifically:

- **In-Revit Assistant (Anthropic or OpenAI, your choice).** When you send a prompt in the Connect pane, the Software transmits to the provider you selected: your prompt, the conversation so far, and the results of the tools the Assistant runs to answer you. Those results are the **model data the tools read**: element counts, element ids, QA findings, and the names of elements, views, sheets, levels, worksets and links you ask about (and the values of parameters and the schedule rows you ask about, and the specification table you give it to compare against the model). Reading values is the one place where your project's own text, for example a manufacturer or a door mark, travels to the provider: ask only about what you are willing to share with that provider. The Software never sends full file paths, Windows user names or model geometry to the provider. The request goes over the provider's own encrypted connection, directly from your machine.
- **Voice dictation (OpenAI).** When you click the microphone, the recorded **audio** is uploaded to OpenAI with your OpenAI key to be transcribed into text. Audio is captured only while you are dictating. Without an OpenAI key, Windows' built-in speech recognition is used instead and no audio leaves your computer.
- **The embedded documentation index is offline.** When the Assistant explains a command, it reads the copy of the documentation shipped inside the add-in; no network request is made for that lookup.
- **External MCP clients (Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI, others).** The companion MCP server hands tool results to the client running on **your** computer, over the local named pipe. The client then sends them to **its own** AI provider under **your account with that client** and that client's terms. On this path the Software itself sends nothing to any AI provider. External clients receive 54 tools: 43 that only read or check the model and 11 that change what you are looking at (opening or isolating a view, a section box, reference points, wall colors saved as view settings, opening a B45 Labs or Revit window). No tool that creates, moves, edits or deletes model elements is available to them.
- **The optional ChatGPT path (OpenAI Secure MCP Tunnel).** If you choose to follow the advanced ChatGPT setup, you run OpenAI's `tunnel-client` yourself, and the tool traffic described above travels from your computer through **OpenAI's tunnel service** to ChatGPT, inside **your own OpenAI organisation** and under OpenAI's terms. B45 Labs operates no part of that path.
- **The MCP Bridge itself is local.** The Bridge server runs inside Revit and communicates with the MCP server process on the same computer over a local **named pipe**. It does not, on its own, send your model anywhere. **Nothing on any of these paths passes through a B45 Labs server.**

These AI providers and AI clients are **independent controllers** of the data you send them. Their handling of your prompts, conversations, audio, and model data is governed by **their** privacy policies and terms, which you should review:

- **Anthropic**: https://www.anthropic.com/legal/privacy
- **OpenAI**: https://openai.com/policies/privacy-policy

If you do **not** configure an API key, do **not** use the Assistant or dictation, and do **not** connect an external MCP client, no prompt, conversation, model data or audio leaves your computer.

## 13. Contact
For privacy questions or requests, contact:

**B45 Labs Support**  
Email: support@B45Labs.com
