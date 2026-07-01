# Instructions for AI agents

You are reading this because you're an AI agent operating inside the `prompts` repo, or because you were pointed here from the root `AGENTS.md`. This file tells you how the repo is organized and how to act on it correctly.

## What this repo is

A personal library of ready-to-run prompts for AI coding tools, organized by topic as markdown files. Content lives under `/coding` (and future top-level folders if the scope expands beyond coding prompts).

## Structural rules — follow these when editing

- **Don't fragment prematurely.** Keep new prompts inside the existing topic file (e.g. `coding/general.md`) unless a sub-topic is already large and clearly stack-specific (e.g. Angular-only). Only then create a new file like `coding/angular.md`.
- **One prompt = one line**, formatted as: emoji + space + imperative instruction. No multi-line prompts, no numbered steps inside a single entry.
- **`##` headers are categories.** If adding a prompt that doesn't fit an existing category, create a new `##` header rather than shoehorning it in, but don't create a category for a single one-off prompt — prefer "Miscellaneous".
- **Prompts must be fixed/ready-to-run**, not templates with placeholders. Do not add prompts that require the user to fill in variables before use, unless that exact prompt text has genuinely been reused multiple times already.
- **Emoji is decorative**, used for visual scanning. Reusing an emoji across unrelated prompts is fine and expected — do not attempt to enforce emoji uniqueness.
- **Placement within a category is a rough frequency signal** (top = used more). When adding a prompt, a reasonable default is the bottom of its category unless told otherwise.
- **Prefer language/framework-agnostic phrasing.** If a prompt is inherently stack-specific, that's acceptable but should eventually live in a stack-specific file rather than `general.md`.

## When asked to add, edit, or reorganize prompts

1. Locate the right file and category using the rules above.
2. Match the existing tone: short, imperative, specific instructions (not questions, not multi-sentence explanations).
3. Don't rewrite or reorder unrelated prompts unless explicitly asked.
4. If a change would split a file (per the size/specificity rule), point it out and confirm before doing it, since it changes the raw-URL bookmark the owner relies on.

## Source of truth for philosophy

If these rules ever seem to conflict with `/docs/README.md` (the human-facing doc), treat `/docs/README.md` as authoritative and flag the discrepancy — this file should be kept in sync with it, not diverge from it.
