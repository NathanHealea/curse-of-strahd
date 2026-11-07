Create or update an NPC profile for: $ARGUMENTS

1. Check `02-characters/npc/` for an existing profile for this NPC.
2. If the profile exists, update it with any new information from recent sessions in `01-sessions/`.
3. If the profile does not exist, create a new one using the established format: key facts, relationships, and notable interactions with the party.
4. Use `[[wiki-links]]` for cross-references to other characters, places, and events.
5. Save to `02-characters/npc/{name}.md` (lowercase kebab-case filename).

New notes start from `_templates/npc.md`. Keep the YAML frontmatter accurate (status, disposition, location, sessions, etc.) and add any alternate spellings to `aliases`. When finished, run `python3 .claude/scripts/build_index.py` to refresh the indexes.
