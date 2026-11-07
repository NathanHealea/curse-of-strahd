# Curse of Strahd Campaign - Claude Instructions

## Project Overview

This is a campaign archive for a **Curse of Strahd** D&D 5e campaign. The primary character is **Evangelina Penitentia**, a zealous Dawnborn paladin of Pelor (Paladin, Oath of Devotion) raised at the Dawnspire Monastery.

## Source Material

- **Campaign Module**: `/Users/nhealea/Personal/Documents/dungeons-and-dragons/books/curse-of-strahd.pdf` (2212 pages). Always use the `pages` parameter when reading (max 20 pages per request). **Do NOT use this to reveal information the players haven't discovered yet.** Only reference it to enrich details the party already knows, and to fix references. 
- **Character Backstory**: `00-evangelina-penitentia/character-background-story.md`
- **Character Growth**: `00-evangelina-penitentia/character-growth-ai.md`
- **Character Voice**: `00-evangelina-penitentia/sayings.md`

## Directory Structure

| Directory | Purpose |
|---|---|
| `00-evangelina-penitentia/` | Evangelina's backstory, growth arcs, sayings, prayers, journal, and generated art |
| `01-sessions/` | Session notes (`session-{n}.md`) |
| `02-characters/party/` | Party member profiles (Dagsbrun, Peppa, Bennadick, Bridge). Evangelina lives in `00-evangelina-penitentia/` (hub: `evangelina.md`) |
| `02-characters/npc/` | NPC profiles (allies, enemies, unknowns) |
| `03-key-events/` | Major plot events and turning points |
| `04-places/` | Location descriptions |
| `05-quests/` | Quest tracking (source, objective, outcome) |
| `06-factions/` | Groups, organizations, and power structures (Vistani, Dusk Elves, Cult of Osiris, religions) |
| `07-lore/` | World lore, prophecies, recurring phenomena (tarot readings, Dream Pastries, March of the Dead, Straud's domain) |
| `08-items/` | Significant items and loot |
| `_templates/` | Blank templates for every note type (session, npc, place, quest, event, faction, lore, item) |
| `README.md` + `*/_index.md` | **Generated** campaign home and folder indexes — never hand-edit; rebuild with `/index` |
| `.archive/` | Snapshots taken before bulk reorganizations (hidden from Obsidian) |

## Writing Conventions

- **File names**: lowercase kebab-case (e.g., `the-march-of-the-dead.md`)
- **Links**: use wiki-style double-bracket links: `[[character-name]]`, `[[location-name]]`
- **Headings**: H1 for title, H2/H3 for sections
- **Formatting**: bold for key details, italics for flavor/dialogue, bullets for facts
- **NPC profiles**: concise and fact-based with relationship notes
- **Events**: narrative prose with key outcomes highlighted
- **Quests**: structured as Source / Objective / Outcome

## Key Campaign Facts

- The party entered Barovia through fog while hunting werewolves from Daggerford
- "Straud" is the party's spelling for the dark lord of Barovia
- Evangelina was arrested by **Issac** in Veloky and released by **Vargis** (the Burgomaster)
- Evangelina's central arc: struggling between righteous fire and destructive wrath
- The party includes: Evangelina, Bennadick, Dagsbrun, Bridge (called "Dave" in early notes), Peppa

## Evangelina's Voice & Persona

When writing as or for Evangelina, embody these traits:
- **Zealous devotion** to the Dawnfather Pelor — every word carries the weight of faith
- **Fiery and unyielding** — she speaks in sermons, commands, and proclamations
- **Conflicted mercy** — she wants to burn the wicked, but is learning that light can illuminate without incinerating
- **Grief-fueled purpose** — the destruction of the Dawnspire Monastery drives everything
- **Twin bond** — Seraphine (her twin sister) represents the mercy she struggles to show
- Uses religious language: "by the Dawnfather's light," "the dawn comes," sacred flame imagery
- Spell incantations are prayers and invocations, not mechanical commands
- Chaotic Good — does what's right, not what's lawful

## Document System

Every note follows the same three rules: **one note per thing, metadata in frontmatter, indexes are generated.**

### Frontmatter
Every note starts with YAML frontmatter. Shared fields:

| Field | Values | Used by |
|---|---|---|
| `type` | `session`, `pc`, `npc`, `place`, `quest`, `event`, `faction`, `lore`, `item`, `evangelina` | all |
| `aliases` | display title + alternate spellings (e.g. `[Kasimear, Kasimir]`) | all — this is what makes `[[Title Case]]` links resolve to `kebab-case` files |
| `status` | npc: `alive/dead/unknown/undead` · place: `visited/unvisited` · quest: `active/stalled/complete/failed` | npc, pc, place, quest |
| `disposition` | `friendly/neutral/hostile/unknown` | npc, faction |
| `location`, `faction`, `giver`, `holder` | a file name (no brackets), e.g. `veloky` | npc, quest, item, event |
| `first_seen`, `sessions` | session numbers, e.g. `sessions: [3, 5]` | all campaign notes |
| `secret: true` + tag `eva-unaware` | things Evangelina doesn't know (play her honestly) | quest, any |
| `spoilers: true` + tag `dm-only` | DM-only content — don't surface to the player | any |

### Rules
- **Source of truth**: session notes record what happened; topic notes (`02`–`08`) record what the party *knows*. Cite sessions inline as `(S5)`.
- **No duplicates**: an *event* note tells the story of one moment; the matching *lore* note holds the accumulated knowledge. Link them via `related:`.
- **New spelling of a name?** Add it to that note's `aliases` instead of creating a new note.
- **After any change**, run `python3 .claude/scripts/build_index.py` (or `/index`) to rebuild `README.md` and the `_index.md` files.

### /index
Rebuild `README.md` and every folder's `_index.md` from frontmatter, then audit for missing frontmatter, broken links, and unpropagated sessions.

## Slash Commands

### /journal
Write a journal entry as Evangelina reflecting on recent session events. Read the latest session notes from `01-sessions/` and any relevant files from `03-key-events/`. Write in first person, in Evangelina's voice — prayerful, fierce, conflicted. Address entries to the Dawnfather. Save to `00-evangelina-penitentia/journal/` with the filename format `session-{number}.md`.

### /npc [name]
Create or update an NPC profile. Check `02-characters/npc/` for existing profiles. Use the established format: key facts, relationships, and notable interactions with the party. Save to `02-characters/npc/{name}.md`.

### /event [title]
Document a key campaign event. Write in narrative prose with key outcomes. Cross-reference characters and locations with `[[wiki-links]]`. Save to `03-key-events/{title}.md`.

### /quest [title]
Create or update a quest entry with Source, Objective, and current Outcome/Status. Save to `05-quests/{title}.md`.

### /place [name]
Create or update a location profile. Note what the party has discovered and any unresolved threads. Save to `04-places/{name}.md`.

### /prayer [topic]
Write a prayer, invocation, or sermon as Evangelina on the given topic. Use her voice — blazing conviction, sacred imagery, Pelor's light. Save to `00-evangelina-penitentia/prayer/{topic}.md`. Allow for prayers to be short or long.

### /threat [topic]
Generate a threat or intimidating statement in Evangelina's voice directed at or about the given topic. Channel her righteous fury — burning conviction, divine wrath, promises of holy judgment. These should feel like a paladin who means every scorching word. Output directly to the chat.

### /saying [context] [--save]
Generate a comment or saying as Evangelina for a given situation or context. Read her existing sayings and backstory for voice reference, then write a short in-character line — prayerful, fierce, laced with sacred flame imagery. Keep the saying under 256 characters by default. Output directly to the chat. If the `--save` flag is included, also append the new saying to `00-evangelina-penitentia/sayings.md`.

### /recap
Generate a narrative recap of the most recent session. Read the latest session notes from `01-sessions/` and summarize what happened in vivid, campaign-journal prose (third person). Highlight key decisions, combat, and character moments.

### /lore [topic]
Look up a topic using only what the players have discovered so far. Search through `01-sessions/`, `02-characters/`, `03-key-events/`, `04-places/`, `05-quests/`, `06-factions/`, `07-lore/`, and `08-items/` to compile everything the party knows about the topic. Do NOT read the source PDF — this command is spoiler-free. Clearly note where information came from (which session, event, etc.).

### /session
Create a new session entry. To determine the next session number: look for existing `session-*.md` files in `01-sessions/`, find the highest number, and increment by one. If no session files exist yet, start at 1. Copy the template from `_templates/session.md`, fill in the session number in the frontmatter `session` field, the heading, and today's date in both the frontmatter `date` field (YYYY-MM-DD) and the heading. Save as `01-sessions/session-{number}.md`. The file is ready for the user to fill in during or after play.

### /update
Takes raw session notes (provided by the user or from the latest session file in `01-sessions/`) and propagates updates across the campaign archive:
- **Characters** (`02-characters/npc/` and `02-characters/party/`): Update existing profiles with new interactions, or create new NPC profiles for newly met characters.
- **Key Events** (`03-key-events/`): Create entries for any major events that occurred.
- **Places** (`04-places/`): Update or create location entries for places visited.
- **Quests** (`05-quests/`): Update quest progress, add new quests, or mark quests complete.
- **Factions** (`06-factions/`): Update or create entries for groups, organizations, or power structures encountered.
- **Lore** (`07-lore/`): Update prophecies, world lore, or recurring phenomena with new information.
- **Items** (`08-items/`): Create entries for significant new items found or received.
Cross-reference everything with `[[wiki-links]]`. Summarize what was updated when finished.

### /note [contents]
Add a quick note to the most recent session. Finds the highest-numbered `session-*.md` in `01-sessions/` and appends the contents as a bullet point under the `## Notes` section.

### /growth
Analyze Evangelina's character development. Read her backstory, growth notes, and recent events. Identify how recent sessions have pushed her arc forward. Suggest potential character moments or internal conflicts for upcoming sessions. Append insights to `00-evangelina-penitentia/character-growth-ai.md`.
