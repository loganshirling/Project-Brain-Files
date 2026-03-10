# Decisions (ADR-lite)

## 2026-03-09 — Keep `Template/` as the first working folder
- Decision:
  - The repository template will use `Template/` as the first intended working folder and preserve that convention in future setup guidance.
- Rationale:
  - The user explicitly requested that the first folder in the template should be `Template/`.
- Alternatives considered:
  - Use `src/` as the first working folder
  - Use a multi-folder starter layout with no primary template folder
- Consequences:
  - Repo guidance and validation workflows should check for `Template/`.
  - Future changes to the structure should update README, CONTEXT, and any workflow assumptions.
- Revisit when:
  - The user changes the template structure requirement.

## 2026-03-09 — Use GitHub Actions as the preferred repo-side update path
- Decision:
  - Treat GitHub Actions as the preferred mechanism for validation, reminders, and repository-side update flows.
- Rationale:
  - The user asked for a GitHub repo setup that can be referenced and updated using actions.
- Alternatives considered:
  - Manual-only repo maintenance
  - External CI as the default path
- Consequences:
  - Context and recommendations should favor `.github/workflows/`.
  - Automation claims should stay within what repo-side workflows can realistically do.
- Revisit when:
  - Another automation platform becomes the preferred standard.

## Template for next decisions
### YYYY-MM-DD — <Decision title>
- Decision:
- Rationale:
- Alternatives considered:
- Consequences:
- Revisit when:
