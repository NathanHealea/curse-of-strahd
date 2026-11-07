Create or update a location profile for: $ARGUMENTS

1. Check `04-places/` for an existing profile for this location.
2. Note what the party has discovered about this place and any unresolved threads.
3. Search `01-sessions/` for session references to this location for additional context.
4. Use `[[wiki-links]]` for cross-references to characters, events, and other places.
5. Save to `04-places/{name}.md` (lowercase kebab-case filename).

New notes start from `_templates/place.md`. Keep the YAML frontmatter accurate (status, disposition, location, sessions, etc.) and add any alternate spellings to `aliases`. When finished, run `python3 .claude/scripts/build_index.py` to refresh the indexes.
