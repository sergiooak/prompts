# Agent Instructions

Personal prompt library for AI coding tools (GitHub Copilot, Cursor, Claude Code).

## Repo purpose

A collection of reusable one-liner prompts, organized by topic. Not a tool, not a library — just text.

## Structure

- [`coding/general.md`](./coding/general.md) — main prompts file (all coding prompts, grouped by `##` category)
- [`docs/README.md`](./docs/README.md) — philosophy and conventions (read before making structural changes)

> `prompts.txt` is the legacy flat-text version; the canonical source is `coding/general.md`.

## Prompt format

Every prompt is **one line**: an emoji (visual anchor only, not a search key) followed by a clear, imperative, self-contained instruction. No `{{placeholders}}`.

```
🔧 Refactor code to enhance clarity, consistency, and readability, following the styleguide and modern best practices
```

## Adding a prompt

1. Find or create the relevant `##` category in `coding/general.md` (or a new file if warranted — see below).
2. Add one line: `<emoji> <imperative instruction>`.
3. Place it roughly by expected usage frequency within the category (top = more used).
4. Commit: `add: prompt for <short description>`.

## When to create a new file

Only split a section into its own file (e.g. `coding/angular.md`) when it is **both**:
- Large enough to be unwieldy in the general file, **and**
- Specific to a stack/domain that doesn't apply broadly.

Don't split preemptively.

## Conventions

- Categories are `##` headers; they are the primary organization unit.
- Emoji uniqueness is **not** guaranteed — search by keyword, not by emoji.
- Prompts are framework/language-agnostic where possible; stack-specific ones are noted inline (see Angular/RxJS note in `coding/general.md`).
- The repo has no build step, no tests, no CI. Changes are just markdown edits.
