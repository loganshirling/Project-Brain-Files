# Project: GitHub Template Repo with Actions Updates

## Goal
Create a GitHub repository template that is easy to reuse, keeps `Template/` as the first working folder, and uses GitHub Actions as the preferred path for validating or updating repo-side state.

## Scope boundaries
### In scope
- Repository template planning and markdown canon for ChatGPT Project Sources
- Rules for keeping `Template/` as the primary scaffold folder
- Guidance for GitHub Actions-based validation, reminders, and content-maintenance workflows
- Repo conventions, decision logging, and low-drift operating standards

### Out of scope
- Full application code scaffold inside `Template/`
- Secrets management details
- Organization-specific compliance or branch-protection policy not yet provided
- Fully automated sync into ChatGPT Project Sources

## Current priorities (top 3)
1. Lock in the repo structure and the role of `Template/`.
2. Capture how GitHub Actions should be used for updates, checks, and maintenance.
3. Minimize drift between chat decisions, uploaded markdown, and the repository template.

## File map
- Rules: `01__RULES__Operating-Standards.md`
- Style: `02__STYLE__Voice-and-Formatting.md`
- Preferences: `03__USER__Preferences.md`
- Knowledge base: `04__CONTEXT__Domain-Knowledge.md`
- Decisions: `05__DECISIONS__ADR-Lite.md`
- Running log: `06__LOG__RUNNING.md`
- Glossary: `90__REF__Glossary.md`
- Source links: `99__REF__Source-Links.md`

## Assumptions used for this starter set
- GitHub is the canonical repo host.
- The repo should be created or marked as a GitHub template repository.
- GitHub Actions will live in `.github/workflows/`.
- The ChatGPT Project Sources are maintained manually from this repo unless a later integration is added.
