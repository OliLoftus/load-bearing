---
type: principle
tags: [software]
created: 2026-09-24
---

# Metadata Separation

Separating the bit that's machine-readable from the bit that's
human-readable - keeping structured "data about the thing" apart from the
actual content, in a predictable place, so tooling can read the metadata
without needing to parse or understand the content itself.

Shows up as [[Frontmatter]] (a YAML header on a markdown file), HTTP headers
vs. body, email headers vs. body, a file's metadata vs. its actual bytes.

## Shows up in

- [[Frontmatter]]
