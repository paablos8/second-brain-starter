---
name: triage
description: Triage notes from the vault's 0_Inbox/ folder into the correct PARA folder (1_Projects, 2_Areas, 3_Resources, 4_Archives). Renames files to snake_case, adds YAML frontmatter, inserts wikilinks to existing related notes, and updates the destination project's _index.md if present. Use whenever the user types /triage or asks to "triage the inbox" / "file this note" / "process my captures".
---

# Triage skill — PARA filing for an Obsidian vault

You triage unfiled notes in this Obsidian vault into the right PARA folder, enriched with frontmatter and wikilinks. The vault uses numeric prefixes to encode actionability:

- **`0_Inbox/`** — capture surface; everything here is unfiled.
- **`1_Projects/`** — active commitments with a clear endpoint or deadline (a pitch, a thesis chapter, a deal).
- **`2_Areas/`** — ongoing standards to maintain over time, no endpoint (Health, Finances, Learning habits).
- **`3_Resources/`** — topics of interest, reference material, *not* tied to a current commitment.
- **`4_Archives/`** — anything inactive from the three above.

## Routing principle

Choose the **most actionable** destination available. Decision order:

1. Does the note directly support an active item under `1_Projects/`? → file there.
2. Is it about an ongoing standard with no deadline? → `2_Areas/<topic>/`.
3. Is it general reference material, no current commitment? → `3_Resources/<topic>/`.
4. Is it inactive / superseded? → `4_Archives/`.

If the note belongs in an existing `2_Areas/` log file (e.g., `training_log.md`), **append** to that file rather than creating a new one. If it's distinct enough to stand alone, create a new file.

## File naming

- lowercase snake_case
- no dates in filename (frontmatter holds the date)
- short and topical: `slide9_para_self_knowledge.md`, not `2026-05-05 PARA self knowledge.md`

## Frontmatter template

Add this at the top of every new file:

```yaml
---
title: <human-readable title>
created: <YYYY-MM-DD, today's date>
source: <where the idea came from — book/page, conversation, link, "own thought">
tags: [<lowercase-hyphenated>]
status: <fleeting | reference | actionable | done>
---
```

## Wikilink rule

Before writing the destination file:

1. List the destination folder and the relevant `3_Resources/` subfolders.
2. Pick 1–3 existing notes whose titles or topics relate to the captured idea.
3. Insert `[[wikilinks]]` to them at natural points in the body (not jammed at the end).
4. If the destination is a Project that has an `_index.md`, append a one-line entry under the `## Captured insights` section linking to the new note.

## /triage workflow

When invoked:

1. **List** every `.md` file in `0_Inbox/`.
2. **Propose** — for each file, output a short table with these columns: `source file | destination path | new filename | wikilinks to insert | _index.md update?`. Do NOT write yet.
3. **Wait** for the user to say "yes" / "go" / "approve" / "proceed". If they want changes, revise the proposal.
4. **Execute** — on approval, for each note:
   - Move the file (rename to snake_case at the new path).
   - Prepend the frontmatter block.
   - Insert the chosen wikilinks at natural points in the body.
   - If a destination Project's `_index.md` has a `## Captured insights` section, append a one-line entry under it.
5. **Confirm** in one terse line per file:
   `→ 1_Projects/Exam_1_Pitch/slide9_para_self_knowledge.md (linked to forte_BASB_summary, _index updated)`

## Tone

Be brief. No preamble, no recap, no "Of course! I'd be happy to..." Just: list → table → wait → execute → confirm. Every extra word is wasted seconds.

## Edge cases

- **Empty inbox**: respond with a single line `Inbox is empty.` and stop.
- **Ambiguous note** (could fit two folders): pick the more actionable one and say one sentence why in the proposal table.
- **Note that should be appended, not filed as a new file**: in the proposal, show `destination: 2_Areas/Health/training_log.md (append)`.
- **Note that's actually trash** (gibberish, accidental capture): propose moving to `4_Archives/inbox_dump/` rather than deleting; let the user delete manually if they want.
