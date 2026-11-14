# B45 Labs – Terms of Use / End User License Agreement (EULA)

**Effective date:** 2026-01-01  
**Last updated:** 2026-11-13 (section 5 corrected to list the failure reports, the installation record and the coarse region that the Software sends). Earlier, 2026-10-04 (WP-C74 refresh: sections 1, 5 and 6: the Coordination requirement, the no-telemetry statement for this build, two AI providers chosen by you, dictation audio, third-party AI clients and the optional ChatGPT tunnel; section numbering unchanged, including the 8.1 clause that other documents cite)  
**Applies to:** B45 Labs | Connect 1.0.0 (Revit 2023, 2024, 2025, 2026, 2027), an add-on that requires B45 Labs | Coordination 2.2 or newer

This Terms of Use / End User License Agreement (“Agreement”) is a legal agreement between you (“you”, “your”) and B45 Labs (“B45 Labs”, “we”, “our”, “us”) governing your use of the B45 Labs Connect Revit add-in and its companion MCP server (the “Software”).

By installing, copying, or using the Software, you agree to be bound by this Agreement. If you do not agree, do not install or use the Software.

## 1. License Grant
Subject to this Agreement, B45 Labs grants you a limited, non-exclusive, non-transferable, revocable license to install and use the Software for your internal business or personal purposes.

The Software is an add-on to **B45 Labs | Coordination** (version 2.2 or newer), which is licensed under its own agreement and is required for the Software to function. This Agreement covers the Software only.

## 2. Restrictions and Intellectual Property Protection

The Software, its source code, binaries, design, architecture, algorithms, UI flows, telemetry pipeline, and accompanying documentation are the exclusive intellectual property of B45 Labs and are protected by copyright, trade secret, and other applicable intellectual property laws.

You agree **NOT** to, under any circumstance:

- **Reproduce, copy, duplicate, or replicate** the Software, in whole or in part, in any form or by any means, beyond the strictly personal/internal use authorized by Section 1.
- **Reverse engineer, decompile, disassemble, deobfuscate, or otherwise attempt to derive the source code, internal logic, or trade secrets** of the Software, including via static analysis, dynamic instrumentation, memory inspection, network traffic interception, or any equivalent technique. This restriction applies to the maximum extent permitted by applicable law.
- **Surveil, monitor, profile, or otherwise extract** the Software's behavior, telemetry patterns, internal APIs, or workflow logic for the purpose of cloning, competing with, or circumventing the Software.
- **Modify, adapt, translate, or create derivative works** of the Software.
- **Rent, lease, sell, sublicense, distribute, share, publish, or otherwise make the Software available** to third parties, whether for free or for consideration, without prior written authorization from B45 Labs.
- **Remove, obscure, or alter** proprietary notices, trademarks, branding, copyright marks, or attribution embedded in the Software or its documentation.
- **Use the Software to violate** applicable laws, third-party rights, or the rights of any other B45 Labs user.

### 2.1 Enforcement
Any violation of this Section will be considered a material breach of this Agreement and an infringement of B45 Labs' intellectual property rights. B45 Labs reserves the right to pursue, and intends to pursue, all available legal remedies before the competent civil and criminal authorities, including but not limited to:

- injunctive relief to stop the unauthorized conduct,
- recovery of damages and lost profits,
- criminal complaint where the applicable law treats unauthorized reproduction, reverse engineering, or trade secret misappropriation as a criminal offense,
- recovery of attorneys' fees and costs of enforcement.

You acknowledge that monetary damages alone may be insufficient to compensate B45 Labs for a breach of this Section and that B45 Labs is entitled to seek equitable relief without the obligation to post a bond.

## 3. Ownership
The Software is licensed, not sold. B45 Labs retains all right, title, and interest in and to the Software, including all intellectual property rights.

## 4. Updates and Changes
B45 Labs may provide updates, patches, or new versions. The Software may include an update mechanism to notify you of available updates.

Some updates may be required for security, compatibility, or stability reasons. If you choose not to install an update, some features may not work as intended.

Any donation/support links (if present) are optional. Transactions are handled by third-party providers and are subject to their terms.

## 5. Telemetry, Diagnostics, and Privacy
**This build of the Software sends short anonymous reports to B45 Labs**: failure reports (the exception type and code, never a message), usage counts (that a feature was used), one installation record and the coarse region inside it (continent, country and region). It never sends the content of your prompts, the AI's answers, your conversations or your model, and it stops when you turn off **Share anonymous usage data** in B45 Labs | Coordination. Diagnostic information on your computer (a rolling log of tool names, outcomes and timings, and a sanitised error log) is written only to files on your computer and is never transmitted.

The **Privacy Policy** (“Privacy Policy”) describes exactly what is collected and how to turn it off, and a future version that collects more will say so in its release notes before that collection starts. By using the Software, you acknowledge that you have reviewed the Privacy Policy and agree to the handling of information described there.

## 6. Third-Party AI Providers, AI Clients, API Keys, and Costs
The Software's in-Revit AI Assistant and voice dictation work with **third-party AI providers** (**Anthropic** or **OpenAI**, chosen by you) using **your own** API keys. The Software's MCP server works with **third-party AI clients** (such as Claude Desktop, Claude Code, Codex, Cursor, VS Code, Windsurf, Gemini CLI, and ChatGPT through OpenAI's Secure MCP Tunnel) that use **your own** account with that client.

You acknowledge and agree that:

1. **You are responsible for obtaining and managing your own AI provider API keys** and for keeping them confidential and secure. A developer-console API key is pay-per-token and is not a Claude.ai or ChatGPT subscription. B45 Labs does not provide, sell, or manage AI provider accounts or keys, and does not collect or store your keys (see Privacy Policy).
2. **You are solely responsible for any usage, fees, charges, rate limits, or costs** billed by the AI provider(s) or AI client(s) arising from your use of the Assistant, voice dictation, or the MCP server. B45 Labs has no visibility into and no responsibility for provider billing.
3. **Your use of an AI provider is governed by that provider's own terms and policies**, in addition to this Agreement. When you use the Assistant, your prompts, the conversation, and the model data the tools read (element counts, ids, QA findings, and the names of elements, views and sheets you ask about; never full file paths, Windows user names or geometry) are transmitted to the provider you selected, as described in the Privacy Policy. You are responsible for ensuring that transmitting such content complies with your own confidentiality, client, and contractual obligations.
4. **Voice dictation uploads the recorded audio to OpenAI** with your OpenAI key for transcription, only while you are dictating. Without an OpenAI key, Windows' built-in speech recognition is used and no audio leaves your computer.
5. **Third-party AI clients are not part of the Software.** When you connect one through the MCP server, the Software hands tool results to that client on your computer over a local named pipe; the client sends them to its own AI provider under your account with that client and that client's terms. External clients receive non-destructive tools only (reads plus view-state actions); no tool that writes to the model is available to them.
6. **The optional ChatGPT path uses OpenAI's Secure MCP Tunnel.** If you follow it, you operate OpenAI's tunnel software yourself, inside your own OpenAI organisation, and the tool traffic travels through OpenAI's service under OpenAI's terms and plan rules. B45 Labs operates no part of that path and makes no promise about which ChatGPT plans allow it.
7. B45 Labs is not responsible for the availability, accuracy, output, pricing, plan rules, or policies of any third-party AI provider or AI client, or for any interruption or change to their services.

## 7. Support
Support, if any, is provided on a best-effort basis unless you have a separate written support agreement with B45 Labs.

## 8. Third-Party Components
The Software may include third-party libraries or components subject to their own licenses. Where applicable, notices may be provided in “Third-Party Notices” documentation.

## 9. Disclaimer of Warranties

### 8.1 No Professional Services; Mandatory User Double-Check; AI Output Is Not Reliable Without Review; No Liability for On-Site Outcomes

The Software is a **productivity and auditing aid** and does **not** provide professional architectural, engineering, surveying, construction-management, or legal services. B45 Labs is not acting as the Architect/Engineer of Record (AOR/EOR), as a technical authority, or as a consultant for any project, regardless of how its outputs are used.

Outputs, flags, checks, AI-generated answers and suggestions, actions performed through the AI Assistant or the MCP Bridge, sheets, schedules, and any other reports generated by the Software:

- may be **incomplete**, **inaccurate**, **partial**, **context-dependent**, or **based on assumptions** that do not hold for your specific project;
- **AI-generated content in particular may be wrong, fabricated ("hallucinated"), or misleading**, may misinterpret your model or intent, and may propose or perform actions that are not appropriate for your project;
- may fail to detect issues that a human reviewer would catch, or may flag false positives;
- depend entirely on the quality, completeness, and correctness of the input Revit model: "garbage in, garbage out" applies fully;
- are **never to be relied upon as the sole basis** for any design, coordination, fabrication, procurement, or construction decision.

**Mandatory user verification (double-check).** You expressly acknowledge and agree that:

1. Every output of the Software, including every AI-generated answer, suggestion, and any action taken through the Assistant or the MCP Bridge, **must be independently reviewed, cross-checked, and validated by you**, or by a qualified professional under your responsibility, before being used for any project deliverable, coordination action, fabrication order, construction activity, or contractual submission.
2. Such double-check is a **non-delegable obligation** that remains entirely with you, the user. The Software does **not** perform, replace, or reduce this obligation in any way.
3. You will treat the Software's output as a **starting point**, never as a final certification. You remain responsible for any change the AI Assistant or an MCP client makes to your model.

**No liability for on-site / construction-phase outcomes.** To the maximum extent permitted by applicable law, B45 Labs **disclaims any and all liability** for losses, damages, defects, rework, delays, schedule impacts, cost overruns, personal injury, property damage, contractual disputes, or any other consequence arising on the construction site, during fabrication, during procurement, during commissioning, or at any other downstream stage of a project, that may be related, directly or indirectly, to the use of, reliance on, or absence of independent verification of any Software output, including any AI-generated output.

You acknowledge that the Software is **not a substitute** for professional judgment, coordination protocols, BIM Execution Plan procedures, drawing approval workflows, or formal QA/QC processes. Use of the Software does **not** reduce, shift, or transfer in any way your professional and contractual responsibility for the correctness of the project.

THE SOFTWARE IS PROVIDED "AS IS" AND "AS AVAILABLE", WITHOUT WARRANTIES OF ANY KIND, EXPRESS OR IMPLIED.

TO THE MAXIMUM EXTENT PERMITTED BY LAW, B45 LABS DISCLAIMS ALL WARRANTIES, INCLUDING IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, ACCURACY, AND NON-INFRINGEMENT.

## 10. Limitation of Liability
TO THE MAXIMUM EXTENT PERMITTED BY LAW, IN NO EVENT WILL B45 LABS BE LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, OR EXEMPLARY DAMAGES, INCLUDING LOSS OF PROFITS, LOSS OF DATA, BUSINESS INTERRUPTION, OR PROCUREMENT OF SUBSTITUTE SERVICES, ARISING OUT OF OR RELATED TO YOUR USE OF THE SOFTWARE.

B45 LABS’ TOTAL LIABILITY FOR ANY CLAIM RELATED TO THE SOFTWARE WILL NOT EXCEED THE AMOUNT YOU PAID FOR THE SOFTWARE (IF ANY) DURING THE 12 MONTHS PRIOR TO THE EVENT GIVING RISE TO THE CLAIM.

## 11. Termination
This Agreement is effective until terminated. B45 Labs may terminate this Agreement if you breach any term. Upon termination, you must stop using the Software and uninstall/remove all copies in your possession or control.

## 12. Compliance and Export
You agree to comply with all applicable laws and regulations, including export control laws, if applicable.

## 13. Governing Law
This Agreement is governed by the laws of the jurisdiction where B45 Labs is primarily established, without regard to conflict of law principles.

## 14. Entire Agreement
This Agreement and the Privacy Policy constitute the entire agreement between you and B45 Labs regarding the Software and supersede prior or contemporaneous agreements and communications.

## 15. Contact
For questions about this Agreement:

**B45 Labs Support**  
Email: support@B45Labs.com
