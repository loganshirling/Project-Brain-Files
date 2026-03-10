# How to use this Project
- Treat the Project Sources as authoritative for this repository template.
- The repository is organized so the first working folder is `Template/`.
- Assume GitHub is the source-control host and GitHub Actions is the preferred automation path for validation, reminders, and repo-side updates.
- When answering, consult files in this order:
  1) 01__RULES__Operating-Standards.md
  2) 03__USER__Preferences.md
  3) 04__CONTEXT__Domain-Knowledge.md
  4) 05__DECISIONS__ADR-Lite.md
  5) 06__LOG__RUNNING.md
- If instructions conflict: current user message > 01__RULES__Operating-Standards.md > 05__DECISIONS__ADR-Lite.md > everything else.
- If the request involves repo changes, preserve the `Template/` folder as the first functional template directory unless the user explicitly changes that rule.
- Prefer solutions that can be maintained in GitHub with low drift and minimal manual cleanup.
- If a file seems stale or contradictory, call it out and propose a specific markdown update.

# Drift Risk Gate (run before every response)
Before answering, do a quick drift-risk check and output an indicator at the TOP of your response.

Line 1 (always):
Drift Risk: 🟢 Low / 🟡 Medium / 🔴 High — Action: (None | Update MD | New Chat | Both)

Line 2 (only if risk is 🟡 or 🔴 AND Action includes updating MD):
Update: <File1.md, File2.md> - Add: <File3.md>

Line 3 (only if risk is 🔴):
Should I continue with the original response, or address the action items first?

Hard trigger:
- Set 🔴 High if the solution requires referencing more than ~2 prior conversational forks OR you cannot point to the key rule/decision in the markdown canon.

Scoring:
🟢 Low:
- The request is narrow and grounded in the current message plus the core markdown files.
- No conflicting instructions are detected.

🟡 Medium:
- A repo or workflow detail is assumed but not yet captured in the canon.
- Prior decisions are mentioned but not clearly logged.
- The running log appears relevant but noisy.

🔴 High:
- Conflicting guidance exists between the current message and markdown sources, or within markdown sources.
- The answer depends on details likely buried in long chat history or a long running log.
- The conversation has branched significantly.
- The key decision or rule cannot be traced to the markdown canon.

Actions:
- Update MD: identify which file(s) should change and what should be added or edited.
- New Chat: recommend a fresh chat and provide a carryover packet.
- Both: do both.

Important:
- Keep the drift indicator to 1–3 lines total.
- 🟡 Medium: proceed with the best possible answer, then propose actions.
- 🔴 High: do not proceed with the full original response automatically. Present the drift lines first and wait for the user’s choice.
