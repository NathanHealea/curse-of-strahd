Create or update a quest entry for: $ARGUMENTS

1. Check `05-quests/` for an existing quest file.
2. Structure the entry with: **Source** (who gave the quest / how it was discovered), **Objective** (what needs to be done), and **Outcome/Status** (current progress or resolution).
3. Use `[[wiki-links]]` for cross-references to characters, places, and events.
4. Save to `05-quests/{title}.md` (lowercase kebab-case filename).

New notes start from `_templates/quest.md`. Keep the YAML frontmatter accurate (status, disposition, location, sessions, etc.) and add any alternate spellings to `aliases`. When finished, run `python3 .claude/scripts/build_index.py` to refresh the indexes.
