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
  in - a web-clipped page, a one-line question, or a whole themed dump of raw
  material (e.g. concepts pulled from another repo) all land here as-is; run
  `/learning-note-formatting` later to clean up and promote into `Notes/`.
- `Literature/` - notes tied to a specific source (book, course, article).
- `Foundations/Backlog.md` - a plain checklist of things found but not yet
  learned/written up - either surfaced by `/learning-foundations`' own scan,
  or queued directly (e.g. candidate principles spotted while triaging a big
  capture). Never contains generated note content, only checklist lines.
- `Templates/` - starting frontmatter/structure for each note type.

Every note carries frontmatter (`type`, `tags`, `created`) and links to other
notes with native Obsidian `[[wikilinks]]`. Linking to a concept that doesn't
have a note yet is expected - that's exactly the signal `/learning-foundations`
looks for.

## The two skills

- **`/learning-foundations`** - for an actual learning session, not tidying.
  Two ways in: run its scan (missing prerequisite concepts, empty MOC
  sections, undeveloped principles) and pick from what it finds plus the
  backlog, or point it directly at something - a fleeting capture, a backlog
  line, or a topic you just name. Either way it asks what you already know,
  discusses it, and - every time, not just when a pattern's obvious across
  several notes - explicitly asks whether there's a more general principle
  underneath the specific thing. Only writes a note once you can explain it
  (and the principle, if one emerged) back in your own words. Anything found
  but not picked this run stays in `Foundations/Backlog.md` as a checklist
  line, never as a stub note.
- **`/learning-note-formatting`** - hand it a rough note (usually from
  `Fleeting/`) and it applies frontmatter, dedupes against existing concepts,
  splits multi-idea input, normalises tags, and links the result into the
  right MOC section - asking first if no existing section fits.

## Day-to-day workflow

1. **Capture** - something worth keeping strikes you mid-work, or you clip a
   page with the Obsidian Web Clipper, or you dump a big pile of raw material
   (e.g. concepts pulled from another repo) → lands in `Fleeting/` as-is. Zero
   formatting effort, just don't lose it. A big dump gets grouped into a few
   themed captures rather than one file per line, so it stays scannable.
2. **Format** - periodically, run `/learning-note-formatting` on what's piled
   up in `Fleeting/`.
3. **Learn** - when you want an actual learning session, run
   `/learning-foundations` - either let it scan for gaps, or point it
   straight at a fleeting capture, a backlog line, or a topic you name. Same
   flow either way: what do you know, discuss it, find the underlying
   principle if there is one, only write once you can explain it back.
4. **Backlog** - anything found (by the scan, or spotted while triaging a big
   capture) that you don't tackle this session goes in
   `Foundations/Backlog.md` as a checklist line - picked up next time, or
   pointed at directly whenever.
5. **Recall** - any time, just ask Claude directly ("what do I know about
   X") - no command needed, it reads the vault directly since it's plain
   markdown in a git repo.
6. **Commit** - after a formatting or foundations session, commit; push
   whenever you're comfortable sharing that batch.

## Scope

Software/technical notes only. This repo has (or will have) a public remote,
so anything employer-specific is deliberately kept out.
