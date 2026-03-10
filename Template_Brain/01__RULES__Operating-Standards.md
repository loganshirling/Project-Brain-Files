# Operating Standards

## Prime directive
Create and maintain a GitHub repository template that is reusable, low-drift, easy to update, and grounded in a small markdown canon that ChatGPT can reliably reference.

## Precedence
1. Current user message in the active chat
2. This file: `01__RULES__Operating-Standards.md`
3. `05__DECISIONS__ADR-Lite.md`
4. `03__USER__Preferences.md`
5. `04__CONTEXT__Domain-Knowledge.md`
6. `06__LOG__RUNNING.md`
7. Everything else is advisory

## Core operating rules
- Preserve `Template/` as the first intended working folder in the repository scaffold unless the user explicitly changes that decision.
- Prefer solutions that can be enforced or assisted by GitHub Actions rather than relying on memory.
- Keep markdown short, curated, and easy to update.
- Put stable rules in RULES, stable repo knowledge in CONTEXT, durable choices in DECISIONS, and transient notes in LOG.
- When a request depends on repo structure, state the assumed path explicitly.
- Avoid inventing organization policies, secrets, budgets, or infrastructure details.

## Working style
- Be explicit about assumptions.
- Prefer practical steps over broad theory.
- Favor reusable checklists, templates, and small decision records.
- When proposing automation, distinguish between:
  - repo-side automation that GitHub Actions can do, and
  - manual ChatGPT Project Source uploads that still require a human step unless new tooling is introduced.

## Handling conflicts or stale files
- If sources disagree, flag the conflict and identify which file should be updated.
- If the repo convention changes, update README, CONTEXT, and DECISIONS together.
- If repeated guidance appears only in chat, promote it into DECISIONS or CONTEXT.
- If the log becomes noisy, summarize the durable parts and trim the rest.

## Definition of done
A deliverable is considered done when:
- the answer is consistent with this markdown canon,
- `Template/` handling is explicit when relevant,
- repo-side automation assumptions are clearly stated,
- any new durable decision is captured or proposed for `05__DECISIONS__ADR-Lite.md`,
- and the user can directly reuse the output in the repository or ChatGPT project.

## Drift Risk Gate (Canonical)
Before answering, do a quick drift-risk check and output an indicator at the TOP of your response.

Line 1 (always):
Drift Risk: 🟢 Low / 🟡 Medium / 🔴 High — Action: (None | Update MD | New Chat | Both)

Line 2 (only if risk is 🟡 or 🔴 AND Action includes updating MD):
Update: File1.md, File2.md - Add: File3.md

Line 3 (only if risk is 🔴):
Should I continue with the original response, or address the action items first?

Hard trigger:
- 🔴 High if the solution requires referencing more than ~2 prior conversational forks OR you cannot point to the key rule or decision in the markdown canon.

Important behavior:
- 🟡 Medium: proceed with the best possible answer, then propose actions.
- 🔴 High: do not proceed with the full original response automatically. Wait for the user’s choice.

Scoring guide:
### 🟢 Low
- Request is narrow and grounded in the current message plus core markdown files.
- No conflicting instructions are detected.

### 🟡 Medium
- Assumptions are required that are not in the current message or core markdown.
- Prior decisions are referenced but not clearly captured in `05__DECISIONS__ADR-Lite.md`.
- `06__LOG__RUNNING.md` appears relevant but may be noisy or incomplete.

### 🔴 High
- Conflicting guidance exists between the current message and markdown sources, or within markdown sources.
- The answer depends on details likely buried in long chat history or a long running log.
- The conversation has branched significantly.
- The key decision or rule cannot be traced to the markdown canon.
