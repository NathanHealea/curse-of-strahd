Rebuild the Evangelina home page, the campaign home page, and every folder index.

1. Run `python3 .claude/scripts/build_index.py` from the vault root.
2. Then audit the archive and report (don't fix unless asked):
   - Notes missing YAML frontmatter
   - `[[wiki-links]]` that don't resolve to a file name or an `aliases` entry
   - Session files whose events haven't been propagated with /update
