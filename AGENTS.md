# Agent Instructions

Personal prompt lib, AI coding tools (GitHub Copilot, Cursor, Claude Code).

## Repo purpose

Reusable one-liner prompts, by topic. Not tool, not lib — text only.

## Structure

- [`coding/general.md`](./coding/general.md) — main prompts file, grouped by `##` category
- [`docs/README.md`](./docs/README.md) — philosophy + conventions, read before structural change

> `prompts.txt` = legacy flat-text; canonical = `coding/general.md`.

## Prompt format

One line: emoji (visual anchor, not search key) + imperative self-contained instruction. No `{{placeholders}}`.

```
🔧 Refactor code to enhance clarity, consistency, and readability, following the styleguide and modern best practices
```

## Adding a prompt

1. Find/create `##` category in `coding/general.md` (or new file — see below).
2. One line: `<emoji> <imperative instruction>`.
3. Place by expected usage freq (top = more used).
4. Commit: `add: prompt for <short description>`.

## When to create a new file

Split into own file (e.g. `coding/angular.md`) only if **both**: unwieldy in general file, **and** stack/domain-specific, not broad.

Don't split preemptively.

## Claude Code Skills

Skills live in [`.claude/skills/`](./.claude/skills/) — standard convention. Skill = dir + `SKILL.md`.

No `.agents/`, no junction/symlink. `.claude/skills/` = single source, edit direct.

## Conventions

- `##` headers = primary org unit.
- Emoji uniqueness **not** guaranteed — search by keyword.
- Prompts framework/lang-agnostic where possible; stack-specific noted inline (Angular/RxJS note in `coding/general.md`).
- No build, no tests, no CI. Just markdown edits.
