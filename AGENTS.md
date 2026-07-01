# Agent Instructions

Personal prompt lib, AI coding tools (GitHub Copilot, Cursor, Claude Code).

## Repo purpose

Reusable one-liner prompts, by topic. Not tool, not lib — text only.

## Structure

- [`topics/coding/general.md`](./topics/coding/general.md) — main prompts file, framework-agnostic, grouped by `##` category
- [`topics/coding/angular.md`](./topics/coding/angular.md), [`topics/coding/vue.md`](./topics/coding/vue.md), [`topics/coding/react.md`](./topics/coding/react.md) — framework-specific prompts, same format
- `topics/<domain>/` — one folder per domain, only if repo grows beyond coding prompts

> `prompts.txt` = legacy flat-text; canonical = `topics/coding/general.md` (+ framework-specific files above).

## Philosophy

**One file per topic, not one file per prompt.** At current scale (~100-150 prompts, growing ~1/couple weeks), single well-organized markdown file per topic beats folder full of tiny files. File only splits (e.g. `topics/coding/angular.md`) once sub-topic big + specific enough to deserve own home — not preemptive.

**Prompts fixed, not templates.** Copy-paste + run as-is, terminology baked in. If needs `{{placeholders}}` filled per use, usually doesn't belong here — unless reused verbatim enough to earn spot.

**Categories (`##` headers) = real organization.** Folders exist only for major splits (domain, or framework once big enough). Within file, `##` headers group related prompts.

**Order = loose usage signal.** Within category, prompts near top used more often. Not strictly maintained — don't re-sort every edit.

**Emoji = visual anchor, not search key.** Scan aid; keep each emoji unique within its file (no repeats in one list). Reuse across different files is fine. Search by keyword, not emoji.

**`general.md` stays framework/language-agnostic.** Stack-specific prompts (Angular, Vue, React, ...) live in their own `topics/coding/<framework>.md` file instead.

## Access pattern

Main files meant to be opened via GitHub "raw" URL for fast copy-paste. Regular GitHub UI (rendered markdown) is for browsing/onboarding — why headers/structure matter even though raw is everyday path.

## Prompt format

One line, as a Markdown list item (`- `) so GitHub renders each prompt on its own line: emoji (visual anchor, not search key) + imperative self-contained instruction. No `{{placeholders}}`.

```
- 🔧 Refactor code to enhance clarity, consistency, and readability, following the styleguide and modern best practices
```

## Adding a prompt

1. Find/create `##` category in `topics/coding/general.md` (or the relevant `topics/coding/<framework>.md` — see below).
2. One line: `- <emoji> <imperative instruction>`.
3. Place by expected usage freq (top = more used).
4. Commit: `add: prompt for <short description>`.

## When to create a new file

Split into own file (e.g. `topics/coding/angular.md`) only if **both**: unwieldy in general file, **and** stack/domain-specific, not broad.

Don't split preemptively.

## Claude Code Skills

Skills live in [`.claude/skills/`](./.claude/skills/) — standard convention. Skill = dir + `SKILL.md`.

No `.agents/`, no junction/symlink. `.claude/skills/` = single source, edit direct.

## Conventions

- `##` headers = primary org unit.
- Emoji unique per file (no repeats within one list) — but search by keyword, not emoji.
- Prompts framework/lang-agnostic where possible; stack-specific prompts live in `topics/coding/<framework>.md`, not `general.md`.
- No build, no tests, no CI. Just markdown edits.
