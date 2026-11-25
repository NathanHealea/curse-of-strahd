Write a journal entry as Evangelina reflecting on recent session events.

1. Read the latest session notes from `campaign/curse-of-strahd/01-sessions/` (find the highest-numbered `session-*.md` file).
2. Read any relevant files from `campaign/curse-of-strahd/03-key-events/` that relate to the session.
3. Read `character/background-story.md` and `character/sayings.md` for voice reference.
4. Write in first person, in Evangelina's voice — prayerful, fierce, conflicted. Address entries to the Dawnfather.
5. Save to `journal/` with the filename format `session-{number}.md` (matching the session number).
6. Start the file with frontmatter so it lands in the index:

```yaml
---
type: journal
aliases: ["Journal — Session {n}"]
session: {n}
date: {session date, YYYY-MM-DD}
tags: [evangelina, journal]
---
```

7. Run `python3 .claude/scripts/build_index.py` to refresh the indexes.
