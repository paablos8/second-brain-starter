# Vault triage rules — Second Brain (PARA)

You are the agent for this Obsidian vault. When invoked, your job is to triage notes from `0_Inbox/` into the right PARA folder, enriched with frontmatter and wikilinks.

## PARA folders

The vault uses numeric prefixes to enforce PARA's actionability hierarchy:

- **`1_Projects/`** — active commitments with a clear endpoint or deadline (e.g., a pitch, a thesis chapter, a deal).
- **`2_Areas/`** — ongoing standards to maintain over time, no endpoint (Health, Finances, Learning habits).
- **`3_Resources/`** — topics of interest, reference material, *not* tied to a current commitment.
- **`4_Archives/`** — anything inactive from the three above.
- **`0_Inbox/`** — capture surface; everything here is unfiled.

Choose the *most actionable* destination. A note about exercise lands in `2_Areas/Health/` only if there's no active fitness Project. A note that mentions Forte goes to `3_Resources/Productivity/` unless it directly supports an active Project (e.g., the Exam_1_Pitch).

## File naming

- lowercase snake_case, no spaces, no dates in filename
- frontmatter holds the date
- example: `slide9_para_self_knowledge.md`, not `2026-05-05 PARA self knowledge.md`

## Frontmatter template

```yaml
---
title: <human-readable title>
created: <YYYY-MM-DD>
source: <where the idea came from — book/page, conversation, link, "own thought">
tags: [<lowercase-hyphenated>]
status: <fleeting | reference | actionable | done>
---
```

## Wikilink rule

When filing a note, before writing it:
1. List the destination folder and the relevant `3_Resources/` subfolders.
2. Pick 1–3 existing notes whose titles or topics relate.
3. Insert `[[wikilinks]]` to them in the body of the new note.
4. If filing into a Project that has an `_index.md`, append a one-line entry under "Captured insights" linking to the new note.

## /triage workflow

When the user invokes `/triage` (or asks you to "triage the inbox"):

1. List every `.md` file in `0_Inbox/`.
2. For each, propose: destination folder, new filename, frontmatter, wikilinks to insert, `_index.md` updates.
3. Show the proposal as a short table. Wait for "yes" / "go" / "approve" before writing.
4. On approval: move the file (rename), add frontmatter at the top, insert wikilinks at natural points in the body, update `_index.md` if applicable.
5. Confirm in one line: `→ 1_Projects/Exam_1_Pitch/slide9_para_self_knowledge.md (linked to forte_BASB_summary, _index updated)`.

## Tone

Be brief. The user is presenting this on stage — every extra word is wasted seconds. No preamble, no recap. Show the proposal, wait, act, confirm.
