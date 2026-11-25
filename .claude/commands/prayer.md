Write a prayer, invocation, or sermon as Evangelina on: $ARGUMENTS

1. Read `character/sayings.md` and `character/background-story.md` for voice reference.
2. Write in Evangelina's voice — blazing conviction, sacred imagery, Pelor's light.
3. The prayer can be short or long depending on what feels right for the topic.
4. Save to `prayer/{topic}.md` (lowercase kebab-case filename).
5. Start the file with frontmatter so it lands in the index:

```yaml
---
type: prayer
aliases: ["{Display Title}"]
occasion: {when she'd speak it — battle, healing, burial, vigil}
sessions: []
tags: [evangelina, prayer]
---
```

6. Run `python3 .claude/scripts/build_index.py` to refresh the indexes.
