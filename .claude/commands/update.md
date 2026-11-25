Propagate session updates across the campaign archive.

If the user provided raw session notes below, use those. Otherwise, read the latest session file from `campaign/curse-of-strahd/01-sessions/` (highest-numbered `session-*.md`).

$ARGUMENTS

Update ALL of the following areas based on the session content:

1. **Characters** (`campaign/curse-of-strahd/02-characters/npc/` and `campaign/curse-of-strahd/02-characters/party/`): Update existing profiles with new interactions. Create new NPC profiles for any newly met characters.
2. **Key Events** (`campaign/curse-of-strahd/03-key-events/`): Create entries for any major events that occurred.
3. **Places** (`campaign/curse-of-strahd/04-places/`): Update or create location entries for places visited.
4. **Quests** (`campaign/curse-of-strahd/05-quests/`): Update quest progress, add new quests, or mark quests complete.
5. **Factions** (`campaign/curse-of-strahd/06-factions/`): Update or create entries for groups, organizations, or power structures encountered.
6. **Lore** (`campaign/curse-of-strahd/07-lore/`): Update prophecies, world lore, or recurring phenomena with new information.
7. **Items** (`campaign/curse-of-strahd/08-items/`): Create entries for significant new items found or received.

Cross-reference everything with `[[wiki-links]]`. New notes start from the matching file in `campaign/curse-of-strahd/_templates/`; update frontmatter on every note you touch (add the session number to `sessions`, change `status`/`disposition` when they change, add new spellings to `aliases`). Finally run `python3 .claude/scripts/build_index.py` to rebuild the home pages and the folder `_index.md` files. When finished, summarize what was created or updated.
