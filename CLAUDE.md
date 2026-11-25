# Evangelina Penitentia - Claude Instructions

## Project Overview

This vault belongs to **Evangelina Penitentia**, a zealous Dawnborn paladin of Pelor (Paladin, Oath of Devotion) raised at the Dawnspire Monastery. **She is the subject; campaigns are context.** Her character, voice, journal, and arc live at the root. Each campaign she plays in gets its own archive under `campaign/<campaign-name>/` — currently one: `campaign/curse-of-strahd/` (D&D 5e).

## Source Material

- **Campaign Module**: `/Users/nhealea/Personal/Documents/dungeons-and-dragons/books/curse-of-strahd.pdf` (2212 pages). Always use the `pages` parameter when reading (max 20 pages per request). **Do NOT use this to reveal information the players haven't discovered yet.** Only reference it to enrich details the party already knows, and to fix references. 
- **Character Backstory**: `character/background-story.md`
- **Character Growth**: `character/growth.md`
- **Character Voice**: `character/sayings.md`

## Directory Structure

Evangelina first, campaigns nested beneath her.

| Directory | Purpose |
|---|---|
| `evangelina.md` | Her character hub — the front door to everything about her |
| `character/` | Backstory, growth arc, sayings, spells, DM-only scenarios |
| `journal/` | Her letters to the Dawnfather, one per session (`/journal`) |
| `prayer/` | Prayers, invocations, sermons (`/prayer`) |
| `art/` | Portrait and character sheet PDF |
| `campaign/` | One directory per campaign she plays in |
| `campaign/curse-of-strahd/` | The Curse of Strahd archive — everything below is inside it |
| `campaign/curse-of-strahd/01-sessions/` | Session notes (`session-{n}.md`) |
| `campaign/curse-of-strahd/02-characters/party/` | Party member profiles (Dagsbrun, Peppa, Bennadick, Bridge). Evangelina is **not** here — she lives at the root |
| `campaign/curse-of-strahd/02-characters/npc/` | NPC profiles (allies, enemies, unknowns) |
| `campaign/curse-of-strahd/03-key-events/` | Major plot events and turning points |
| `campaign/curse-of-strahd/04-places/` | Location descriptions |
| `campaign/curse-of-strahd/05-quests/` | Quest tracking (source, objective, outcome) |
| `campaign/curse-of-strahd/06-factions/` | Groups, organizations, and power structures (Vistani, Dusk Elves, Cult of Osiris, religions) |
| `campaign/curse-of-strahd/07-lore/` | World lore, prophecies, recurring phenomena (tarot readings, Dream Pastries, March of the Dead, Straud's domain) |
| `campaign/curse-of-strahd/08-items/` | Significant items and loot |
| `campaign/curse-of-strahd/_templates/` | Blank templates for every note type (session, npc, place, quest, event, faction, lore, item) |
| `README.md`, `campaign/curse-of-strahd/README.md`, `*/_index.md` | **Generated** — Evangelina's home, the campaign home, and folder indexes. Never hand-edit; rebuild with `/index`. Each `_index.md` is a live Dataview table (with a Tags column) of the notes in its own folder, so it stays current between rebuilds |
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
| `type` | `session`, `pc`, `npc`, `place`, `quest`, `event`, `faction`, `lore`, `item`, `evangelina`, `journal`, `prayer` | all |
| `aliases` | display title + alternate spellings (e.g. `[Kasimear, Kasimir]`) | all — this is what makes `[[Title Case]]` links resolve to `kebab-case` files |
| `status` | npc: `alive/dead/unknown/undead` · place: `visited/unvisited` · quest: `active/stalled/complete/failed` | npc, pc, place, quest |
| `disposition` | `friendly/neutral/hostile/unknown` | npc, faction |
| `location`, `faction`, `giver`, `holder` | a file name (no brackets), e.g. `veloky` | npc, quest, item, event |
| `first_seen`, `sessions` | session numbers, e.g. `sessions: [3, 5]` | all campaign notes |
| `secret: true` + tag `eva-unaware` | things Evangelina doesn't know (play her honestly) | quest, any |
| `spoilers: true` + tag `dm-only` | DM-only content — don't surface to the player | any |

### Rules
- **Source of truth**: session notes record what happened; topic notes (`campaign/*/02`–`08`) record what the party *knows*. Cite sessions inline as `(S5)`.
- **No duplicates**: an *event* note tells the story of one moment; the matching *lore* note holds the accumulated knowledge. Link them via `related:`.
- **New spelling of a name?** Add it to that note's `aliases` instead of creating a new note.
- **After any change**, run `python3 .claude/scripts/build_index.py` (or `/index`) to rebuild both home pages and the `_index.md` files.

### /index
Rebuild the Evangelina home (`README.md`), the campaign home, and every folder’s `_index.md` from frontmatter, then audit for missing frontmatter, broken links, and unpropagated sessions.

## Slash Commands

### /journal
Write a journal entry as Evangelina reflecting on recent session events. Read the latest session notes from `campaign/curse-of-strahd/01-sessions/` and any relevant files from `campaign/curse-of-strahd/03-key-events/`. Write in first person, in Evangelina's voice — prayerful, fierce, conflicted. Address entries to the Dawnfather. Save to `journal/` with the filename format `session-{number}.md`.

### /npc [name]
Create or update an NPC profile. Check `campaign/curse-of-strahd/02-characters/npc/` for existing profiles. Use the established format: key facts, relationships, and notable interactions with the party. Save to `campaign/curse-of-strahd/02-characters/npc/{name}.md`.

### /event [title]
Document a key campaign event. Write in narrative prose with key outcomes. Cross-reference characters and locations with `[[wiki-links]]`. Save to `campaign/curse-of-strahd/03-key-events/{title}.md`.

### /quest [title]
Create or update a quest entry with Source, Objective, and current Outcome/Status. Save to `campaign/curse-of-strahd/05-quests/{title}.md`.

### /place [name]
Create or update a location profile. Note what the party has discovered and any unresolved threads. Save to `campaign/curse-of-strahd/04-places/{name}.md`.

### /prayer [topic]
Write a prayer, invocation, or sermon as Evangelina on the given topic. Use her voice — blazing conviction, sacred imagery, Pelor's light. Save to `prayer/{topic}.md`. Allow for prayers to be short or long.

### /threat [topic]
Generate a threat or intimidating statement in Evangelina's voice directed at or about the given topic. Channel her righteous fury — burning conviction, divine wrath, promises of holy judgment. These should feel like a paladin who means every scorching word. Output directly to the chat.

### /saying [context] [--save]
Generate a comment or saying as Evangelina for a given situation or context. Read her existing sayings and backstory for voice reference, then write a short in-character line — prayerful, fierce, laced with sacred flame imagery. Keep the saying under 256 characters by default. Output directly to the chat. If the `--save` flag is included, also append the new saying to `character/sayings.md`.

### /recap
Generate a narrative recap of the most recent session. Read the latest session notes from `campaign/curse-of-strahd/01-sessions/` and summarize what happened in vivid, campaign-journal prose (third person). Highlight key decisions, combat, and character moments.

### /lore [topic]
Look up a topic using only what the players have discovered so far. Search through `campaign/curse-of-strahd/01-sessions/`, `campaign/curse-of-strahd/02-characters/`, `campaign/curse-of-strahd/03-key-events/`, `campaign/curse-of-strahd/04-places/`, `campaign/curse-of-strahd/05-quests/`, `campaign/curse-of-strahd/06-factions/`, `campaign/curse-of-strahd/07-lore/`, and `campaign/curse-of-strahd/08-items/` to compile everything the party knows about the topic. Do NOT read the source PDF — this command is spoiler-free. Clearly note where information came from (which session, event, etc.).

### /session
Create a new session entry. To determine the next session number: look for existing `session-*.md` files in `campaign/curse-of-strahd/01-sessions/`, find the highest number, and increment by one. If no session files exist yet, start at 1. Copy the template from `campaign/curse-of-strahd/_templates/session.md`, fill in the session number in the frontmatter `session` field, the heading, and today's date in both the frontmatter `date` field (YYYY-MM-DD) and the heading. Save as `campaign/curse-of-strahd/01-sessions/session-{number}.md`. The file is ready for the user to fill in during or after play.

### /update
Takes raw session notes (provided by the user or from the latest session file in `campaign/curse-of-strahd/01-sessions/`) and propagates updates across the campaign archive:
- **Characters** (`campaign/curse-of-strahd/02-characters/npc/` and `campaign/curse-of-strahd/02-characters/party/`): Update existing profiles with new interactions, or create new NPC profiles for newly met characters.
- **Key Events** (`campaign/curse-of-strahd/03-key-events/`): Create entries for any major events that occurred.
- **Places** (`campaign/curse-of-strahd/04-places/`): Update or create location entries for places visited.
- **Quests** (`campaign/curse-of-strahd/05-quests/`): Update quest progress, add new quests, or mark quests complete.
- **Factions** (`campaign/curse-of-strahd/06-factions/`): Update or create entries for groups, organizations, or power structures encountered.
- **Lore** (`campaign/curse-of-strahd/07-lore/`): Update prophecies, world lore, or recurring phenomena with new information.
- **Items** (`campaign/curse-of-strahd/08-items/`): Create entries for significant new items found or received.
Cross-reference everything with `[[wiki-links]]`. Summarize what was updated when finished.

### /note [contents]
Add a quick note to the most recent session. Finds the highest-numbered `session-*.md` in `campaign/curse-of-strahd/01-sessions/` and appends the contents as a bullet point under the `## Notes` section.

### /growth
Analyze Evangelina's character development. Read her backstory, growth notes, and recent events. Identify how recent sessions have pushed her arc forward. Suggest potential character moments or internal conflicts for upcoming sessions. Append insights to `character/growth.md`.
