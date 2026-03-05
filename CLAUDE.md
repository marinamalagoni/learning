# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a learning/demo repository for experimenting with Claude Code GitHub Actions integrations. It contains no application source code — only GitHub Actions workflows.

## GitHub Actions Workflows

Two workflows live in `.github/workflows/`:

- **`claude.yml`** — Claude Code PR Assistant. Triggers on issue comments, PR review comments, PR reviews, and new issues. Activates when `@claude` is mentioned in the relevant body/comment. Uses `anthropics/claude-code-action@v1` with `CLAUDE_CODE_OAUTH_TOKEN`.

- **`claude-code-review.yml`** — Automated Claude Code Review. Triggers on pull request events (opened, synchronize, ready_for_review, reopened). Runs the `code-review` plugin from `anthropics/claude-code.git` plugin marketplace via `claude-code-action@v1`.

## Required Secret

Both workflows require `CLAUDE_CODE_OAUTH_TOKEN` to be set as a repository secret.

## User Preferences

- Use CLAUDE.md as the persistent memory file for this project (not the ~/.claude/projects memory directory).
- Explanations and commentary should be given directly in the terminal, not as inline code comments.
- When describing database fields or data structures, always include the field type (e.g. `String`, `Boolean`, `DateTime`).
- The user is learning — always explain technical concepts in plain, simple language. Avoid jargon where possible, and define it when it's unavoidable.
- Use comments generously in all code. Comments should explain *what* the code does and *why* in everyday language, not just restate the syntax.
- When in plan mode, at the start of every task, list all expected to-dos. Cross them out (~~like this~~) as each one is completed.

## Commands

```bash
npm run dev          # Start dev server with Turbopack
npm run build        # Production build
npm run lint         # ESLint via Next.js
npm run test         # Run all tests with Vitest
npm run setup        # First-time setup: install + Prisma generate + migrate
npm run db:reset     # Reset database (destructive)
```