<%*
// Runs when a note is created in 01-sessions (Templater folder template)
// or via "Templater: Create new note from template".
const folder = "campaign/curse-of-strahd/01-sessions";
const self = tp.file.path(true);
const nums = app.vault.getMarkdownFiles()
  .filter(f => f.parent && f.parent.path === folder && f.path !== self)
  .map(f => { const m = f.basename.match(/^session-(\d+)$/); return m ? parseInt(m[1], 10) : NaN; })
  .filter(n => !isNaN(n));
const n = (nums.length ? Math.max(...nums) : 0) + 1;
const today = tp.date.now("YYYY-MM-DD");
await tp.file.move(`${folder}/session-${n}`);
-%>
---
type: session
session: <% n %>
date: <% today %>
tags: [session]
---
# Session <% n %> — <% today %>

## Party Members Present
- [ ] [[Dagsbrun]]
- [ ] [[Peppa]]
- [ ] [[Bennadick]]
- [ ] [[Bridge]]
- [ ] [[Evangelina]]

## Where We Left Off
<!-- Brief reminder of where the party was at the start of this session -->


## What Happened
<!-- Key events in order. Use bullet points or short paragraphs. -->
- 

## Combat / Encounters
<!-- Notable fights, skill checks, or dramatic moments -->
- 

## NPCs Met
<!-- New or returning NPCs and what they said/did -->

| NPC | Notes |
|-----|-------|
|     |       |

## Places Visited
<!-- Locations explored or traveled through -->
- 

## Loot / Items
<!-- Anything found, bought, lost, or given -->
- 

## Quests Updated
<!-- New quests, completed quests, or quest progress -->
- 

## Key Decisions
<!-- Choices the party made that could matter later -->
- 

## Open Threads
<!-- Unanswered questions, loose ends, things to follow up on -->
- 

## Notes
<!-- Anything else worth remembering -->

