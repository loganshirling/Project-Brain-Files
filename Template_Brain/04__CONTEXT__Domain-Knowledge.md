# Domain Knowledge Base

## Overview
This file captures the stable working assumptions for a GitHub repository template that is mirrored into ChatGPT Project Sources. The project uses markdown as the inspectable canon and GitHub Actions as the preferred repo-side automation path.

## Key facts and constraints (last verified: 2026-03-09)
- The repository is intended to be used as a GitHub template repository.
- GitHub template repositories let users create new repositories with the same directory structure, branches, and files.
- GitHub Actions workflow files live in `.github/workflows/`.
- The first intended working folder in the template is `Template/`.
- The markdown Brain Files are the human-readable operating canon for this project.
- Repo-side automation can validate, lint, remind, or update files in the repository, but ChatGPT Project Source uploads are treated as a separate manual synchronization step unless a later integration is added.

## Canonical repository shape
### Minimum structure
- `.github/workflows/`
- `Template/`
- `README.md`
- Brain Files stored in the project source set and optionally mirrored in a docs or governance area of the repository

### Folder intent
- `.github/workflows/`: workflow automation for validation, maintenance, and update flows
- `Template/`: starter content that downstream repos copy when created from the template
- root docs: repo-level explanation and onboarding

## Canonical workflows
### Workflow: Validate template structure
- Inputs:
  - push
  - pull_request
  - workflow_dispatch
- Steps:
  - confirm required paths exist
  - verify `Template/` exists
  - optionally lint markdown or naming conventions
- Outputs:
  - pass/fail signal in GitHub Actions
  - early warning when structure drifts

### Workflow: Scheduled markdown maintenance check
- Inputs:
  - schedule
  - workflow_dispatch
- Steps:
  - inspect changed markdown files
  - compare against expected naming conventions
  - generate a summary of files that may need promotion from LOG to DECISIONS or CONTEXT
- Outputs:
  - issue, summary comment, or artifacts for human review

### Workflow: Manual repo update helper
- Inputs:
  - workflow_dispatch with parameters
- Steps:
  - run a scripted update against repo markdown or scaffold files
  - open a pull request or commit to a branch for review
- Outputs:
  - controlled repo update with audit trail

## Common failure modes
- `Template/` is renamed or buried under another folder
- Automation assumptions are captured in chat but not logged in markdown
- The running log becomes the only place where key decisions live
- GitHub Actions is expected to update systems outside the repository without a real integration path
- Repo conventions change but README, CONTEXT, and DECISIONS are not updated together

## Update rules
- Stable repo rules belong here.
- One-off choices belong in `05__DECISIONS__ADR-Lite.md`.
- Temporary notes belong in `06__LOG__RUNNING.md`.
- External documentation and trusted links belong in `99__REF__Source-Links.md`.

## References
- See `99__REF__Source-Links.md`
- See `90__REF__Glossary.md`
