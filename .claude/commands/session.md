Create a new session entry.

1. Look for existing `session-*.md` files in `campaign/curse-of-strahd/01-sessions/` to find the highest session number.
2. Increment by one to get the new session number. If no session files exist, start at 1.
3. Read the template from `campaign/curse-of-strahd/_templates/session.md`.
4. The template is a **Templater** template (Obsidian runs it automatically when a note is created in `01-sessions/`). When creating the file yourself, render it by hand:
   - Delete the leading `<%* ... -%>` script block entirely
   - Replace every `<% n %>` with the new session number
   - Replace every `<% today %>` with today's date (YYYY-MM-DD, in the user's timezone)
5. Save as `campaign/curse-of-strahd/01-sessions/session-{number}.md`.
6. Confirm the file is ready for the user to fill in during or after play.
