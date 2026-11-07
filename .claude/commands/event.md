Document a key campaign event: $ARGUMENTS

1. Write in narrative prose with key outcomes highlighted.
2. Cross-reference characters and locations with `[[wiki-links]]`.
3. Check `01-sessions/` for relevant session context and `02-characters/` for character details.
4. Save to `03-key-events/{title}.md` (lowercase kebab-case filename).

New notes start from `_templates/event.md`. Keep the YAML frontmatter accurate (status, disposition, location, sessions, etc.) and add any alternate spellings to `aliases`. When finished, run `python3 .claude/scripts/build_index.py` to refresh the indexes.
