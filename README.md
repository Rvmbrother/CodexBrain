# CodexBrain

CodexBrain stores cross-repository learnings for Codex.

## Canonical notebook

- File: `global-notebook.md`
- Branch: `main`
- Remote: `origin`

Agents using `/lfm` should pull this repository at chat start, read `global-notebook.md`, and use it as global context.

## What belongs here

Keep only learnings that are safe across repositories and non-coding contexts.

Use this file for:

- Agent workflow heuristics
- General engineering/debugging patterns
- Generic testing and review guidance
- Reusable templates and delivery hygiene

Do not store repo-specific commands, env vars, CI internals, or schema-specific constraints here.

## Logging protocol

A learning should be added only after explicit confirmation:

- `confirmed log learning`
- `CLL`

Each entry should contain:

- What failed
- Root cause
- Final fix
- Prevention check
- Scope (`global`)
