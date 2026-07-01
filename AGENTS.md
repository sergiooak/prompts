# Agent Instructions

Personal prompt lib, AI coding tools (GitHub Copilot, Cursor, Claude Code).

## Repo purpose

Reusable one-liner prompts, by topic. Not tool, not lib — text only.

## Structure

- [`topics/coding/general.md`](./topics/coding/general.md) — main prompts file, grouped by `##` category
- `topics/<domain>/` — one folder per domain, only if repo grows beyond coding prompts

> `prompts.txt` = legacy flat-text; canonical = `topics/coding/general.md`.

## Philosophy

**One file per topic, not one file per prompt.** At current scale (~100-150 prompts, growing ~1/couple weeks), single well-organized markdown file per topic beats folder full of tiny files. File only splits (e.g. `topics/coding/angular.md`) once sub-topic big + specific enough to deserve own home — not preemptive.

**Prompts fixed, not templates.** Copy-paste + run as-is, terminology baked in. If needs `{{placeholders}}` filled per use, usually doesn't belong here — unless reused verbatim enough to earn spot.

**Categories (`##` headers) = real organization.** Folders exist only for major splits (domain, or framework once big enough). Within file, `##` headers group related prompts.

**Order = loose usage signal.** Within category, prompts near top used more often. Not strictly maintained — don't re-sort every edit.

**Emoji = visual anchor, not search key.** Scan aid; several prompts share same emoji on purpose. Search by keyword, not emoji.

**Prompts aim framework/language-agnostic**, exceptions exist (Angular/RxJS ones) — cleaned up opportunistically, not a blocker to adding content.

## Access pattern

Main files meant to be opened via GitHub "raw" URL for fast copy-paste. Regular GitHub UI (rendered markdown) is for browsing/onboarding — why headers/structure matter even though raw is everyday path.

## Prompt format

One line: emoji (visual anchor, not search key) + imperative self-contained instruction. No `{{placeholders}}`.

```
🔧 Refactor code to enhance clarity, consistency, and readability, following the styleguide and modern best practices
```

## Adding a prompt

1. Find/create `##` category in `topics/coding/general.md` (or new file — see below).
2. One line: `<emoji> <imperative instruction>`.
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
- Emoji uniqueness **not** guaranteed — search by keyword.
- Prompts framework/lang-agnostic where possible; stack-specific noted inline (Angular/RxJS note in `topics/coding/general.md`).
- No build, no tests, no CI. Just markdown edits.
