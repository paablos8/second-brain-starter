# Build Your Second Brain

A starter kit. Clone the vault, plug in Claude, capture your first note tonight.

---

## 1. Install the tools (3 min)

- **Obsidian** (free) → <https://obsidian.md/download>
- **Claude** — pick one:
  - *Easiest:* **Claude.ai Cowork** (web, no install) → <https://claude.ai>
  - *Power user:* **Claude Code** (CLI) → <https://docs.claude.com/en/docs/claude-code/setup>

## 2. Clone the starter vault (2 min)

The vault below is a ready-made PARA structure with seed notes and a triage skill — exactly what I demoed.

```bash
git clone https://github.com/paablos8/second-brain-starter.git
```

Then in Obsidian: **Open folder as vault** → pick the cloned folder.

## 3. Hook Claude up to your vault (3 min)

- **Cowork**: New project → name it *Second Brain* → add the cloned folder under *Context › On your computer*.
- **Claude Code**: open a terminal, `cd` into the vault, run `claude`. The vault's `CLAUDE.md` is auto-loaded.

## 4. Add the `/triage` skill (1 min)

Already inside the repo at `.claude/skills/triage/SKILL.md`.

- **Cowork**: type `/skill-creator` → paste the skill file → name it `triage`.
- **Claude Code**: nothing to do — it picks up the skill from `.claude/skills/`.

## 5. Capture → Triage → Done (1 min)

1. In Obsidian, drop a one-liner into `0_Inbox/`.
2. In Claude, type `/triage`.
3. Approve the proposal. Your note is filed, frontmatter'd, and linked into your existing notes.

That's it. You now have a Second Brain.

---

## 6. (Optional) Capture from your phone via Telegram (15 min)

Turn any Telegram message into a note in `0_Inbox/`. Frictionless capture from anywhere.

1. **Create a bot** — open [@BotFather](https://t.me/BotFather) in Telegram → `/newbot` → save the **bot token**.
2. **Install the plugin** — Obsidian → Settings → Community plugins → search **"Telegram Sync"** (by soberhacker) → install + enable.
   Repo: <https://github.com/soberhacker/obsidian-telegram-sync>
3. **Connect** — plugin settings → paste the bot token.
4. **Route messages to the inbox** — open the **message distribution rule** and set:
   - **Note path template**:
     ```
     0_Inbox/{{messageTime:YYYY-MM-DD-HHmm}}_{{content:30}}.md
     ```
     (timestamp + first 30 chars; sorts chronologically, never collides)
   - **File path template** (only if you'll attach voice/photos):
     ```
     0_Inbox/attachments/{{file:type}}s/{{file:name}} - {{messageTime:YYYYMMDDHHmmssSSS}}.{{file:extension}}
     ```
     Leave empty if text-only.
5. **Test** — start your bot, send a message, confirm the file appears in `0_Inbox/`. Then run `/triage` as usual.

> Caveat: Obsidian needs to be running for the plugin to receive messages. Fine for desktop; for always-on capture you'd need a server bot (out of scope here).

---

## What's inside the starter vault

```
0_Inbox/         ← capture lands here
1_Projects/      ← active commitments with a deadline
2_Areas/         ← ongoing standards (Health, Finances, …)
3_Resources/     ← reference material
4_Archives/      ← inactive
CLAUDE.md        ← the triage contract Claude follows
.claude/skills/triage/SKILL.md   ← the /triage skill
```

## Going further

- Forte, *Building a Second Brain* (2022) — the source.
- Allen, *Getting Things Done* (2001) — the precursor.
- Stefan Imhoff — agentic note-taking with Claude + Obsidian → <https://www.stefanimhoff.de/agentic-note-taking-obsidian-claude-code/>
