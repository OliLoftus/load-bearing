# Learning Vault

A version-controlled Obsidian vault for software/technical learning, using the
Zettelkasten method: small, single-concept notes, densely linked, tied
together by Maps of Content (MOCs). The point isn't a tidy pile of notes - two
Claude Code skills in `.claude/skills/` exist to actually surface what's
missing and help learn it, and to keep the mechanical tidying from being the
reason a note never gets written.

## Structure

- `Notes/` - atomic notes, one concept each, flat (not nested by topic).
  `type: permanent` for a specific fact/concept, `type: principle` for an
  underlying idea other notes depend on (e.g. "least privilege").
- `MOCs/` - Maps of Content. A MOC holds no content of its own, just links out
  to the notes and sub-MOCs that belong to a topic. Start broad (`Software
  MOC`), split into sub-MOCs (`AWS MOC`) once a section gets crowded.
- `Fleeting/` - rough, unprocessed captures. Zero formatting effort on the way
  in; run `/learning-note-formatting` later to clean up and promote into
  `Notes/`.
- `Literature/` - notes tied to a specific source (book, course, article).
- `Foundations/Backlog.md` - a plain checklist of gaps
  `/learning-foundations` has found but that haven't been learned/written up
  yet. Never contains generated note content, only checklist lines.
- `Templates/` - starting frontmatter/structure for each note type.

Every note carries frontmatter (`type`, `tags`, `created`) and links to other
notes with native Obsidian `[[wikilinks]]`. Linking to a concept that doesn't
have a note yet is expected - that's exactly the signal `/learning-foundations`
looks for.

## The two skills

- **`/learning-foundations`** - for an actual learning session, not tidying.
  Scans the vault for gaps (missing prerequisite concepts, empty MOC sections,
  underlying principles implied across notes but never named), merges with the
  backlog, and walks through one gap interactively: asks what you already
  know, discusses it, and only writes a note once you can explain it back in
  your own words. A gap that's found but not picked this run stays in
  `Foundations/Backlog.md` as a checklist line, never as a stub note.
- **`/learning-note-formatting`** - hand it a rough note (usually from
  `Fleeting/`) and it applies frontmatter, dedupes against existing concepts,
  splits multi-idea input, normalises tags, and links the result into the
  right MOC section - asking first if no existing section fits.

## Day-to-day workflow

1. **Capture** - something worth keeping strikes you mid-work → drop a rough
   note in `Fleeting/`. No formatting effort, just don't lose the thought.
2. **Format** - periodically, run `/learning-note-formatting` on what's piled
   up in `Fleeting/`.
3. **Foundations deep-dive** - separately, when you want a real learning
   session, run `/learning-foundations`, pick one gap, work through it
   properly.
4. **Recall** - any time, just ask Claude directly ("what do I know about
   X") - no command needed, it reads the vault directly since it's plain
   markdown in a git repo.
5. **Commit** - after a formatting or foundations session, commit; push
   whenever you're comfortable sharing that batch.

## Scope

Software/technical notes only. This repo has (or will have) a public remote,
so anything employer-specific is deliberately kept out.
