# Docs — how this repo works

This is a personal, growing library of prompts I reuse often with AI coding tools (GitHub Copilot, Cursor, Claude Code). This doc explains the reasoning behind the structure, so future-me (or anyone else) doesn't have to re-derive it.

## Philosophy

**One file per topic, not one file per prompt.** At the current scale (~100-150 prompts, growing by roughly one every couple of weeks), a single well-organized markdown file per topic beats a folder full of tiny files. A file only gets split (e.g. into `coding/angular.md`) once a sub-topic is big and specific enough to deserve its own home — not preemptively.

**Prompts are fixed, not templates.** Everything here is meant to be copy-pasted and run as-is, with correct terminology already baked in. If a prompt needs `{{placeholders}}` filled in per use, it usually doesn't belong here — unless it's been reused verbatim enough times to earn a spot.

**Categories (`##` headers) are the real organization.** Folders exist only for major splits (e.g., by framework, or by domain if this repo ever grows beyond coding prompts). Within a file, `##` headers group related prompts.

**Order is a loose signal of usage.** Within each category, prompts nearer the top tend to be used more often. This isn't strictly maintained — don't worry about re-sorting on every edit.

**The emoji is a visual anchor, not a search key.** It helps you scan the file quickly; several prompts intentionally share the same emoji. Don't rely on emoji uniqueness — search by keyword/phrase instead.

**Prompts aim to be framework/language-agnostic**, but exceptions exist today (e.g. some Angular/RxJS-specific ones) and are cleaned up opportunistically, not as a blocker to adding new content.

## How to add a new prompt

1. Find (or create) the relevant `##` category in the right file under `/coding` (or a future top-level folder if the prompt isn't code-related).
2. Add one line: an emoji + a clear, imperative, self-contained instruction.
3. Place it roughly where its expected usage frequency puts it in the category (top = more used) — don't overthink exact position.
4. Commit with a short, descriptive message (e.g. `add: prompt for auditing API error handling`).

## When to split a file

Split a category out into its own file when it's both (a) large and (b) specific to a stack/domain that doesn't apply broadly — e.g. a growing Angular section becomes `coding/angular.md`. Until then, keep it in the general file.

## Access pattern

The main files are meant to be opened via their GitHub "raw" URL for fast copy-paste into whatever tool you're using. The regular GitHub UI (rendered markdown) is for browsing/onboarding, which is why headers and structure matter even though raw is the everyday path.
