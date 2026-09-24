---
type: permanent
tags: [software]
created: 2026-09-24
---

# Frontmatter

Structured metadata at the top of a file, delimited by `---`, written in
YAML - sitting before the actual content, not part of it.

A specific instance of [[Metadata Separation]]: Obsidian reads `type`,
`tags`, and `created` from a note's frontmatter to organise notes without
reading the prose; Claude Code reads `name` and `description` from a
`SKILL.md`'s frontmatter to decide when to trigger it, without reading the
whole skill body.
