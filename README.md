# Project-Brain-Files

This repository stores ChatGPT Brain Files used to maintain project context, record decisions, and reduce drift over time.

## Purpose

Brain Files are a structured set of markdown files that help ChatGPT keep a consistent understanding of:
- project goals and scope
- rules, constraints, and working standards
- style, user preferences, and domain context
- key decisions and ongoing logs

## Repository workflow

This repository is the source of truth for Brain Files.

Changes should be made through GitHub branches and pull requests:
- never write directly to `main`
- prefer small, reviewable PRs
- read the current file before updating it
- summarize changes clearly in the PR

Brain Files are no longer maintained by downloading, re-exporting, or manually uploading files into the project source.

## Core file structure

Brain Files follow a canonical markdown schema with files such as:
- `00__PROJECT__README.md`
- `01__RULES__Operating-Standards.md`
- `02__STYLE__Voice-and-Formatting.md`
- `03__USER__Preferences.md`
- `04__CONTEXT__Domain-Knowledge.md`
- `05__DECISIONS__ADR-Lite.md`
- recommended: `06__LOG__RUNNING.md`

## Instructions

Repo-specific guidance for how to create, update, and maintain these files is stored in:
- `Instructions/GPT_Instructions.md`

## Goal

The goal of this repo is to keep Brain Files easy to review, easy to update, and reliable as a long-term project memory system.
