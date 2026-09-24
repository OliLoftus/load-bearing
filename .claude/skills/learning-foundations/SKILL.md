---
name: learning-foundations
description: >
  Use when Oliver wants to spend a session actually learning something in this
  vault, not just tidying notes. Either scans Notes/, MOCs/, Literature/,
  Fleeting/ and Foundations/Backlog.md for gaps - missing prerequisite
  concepts, MOC sections with no notes yet, and underlying principles implied
  but never named - or, if Oliver points it directly at something (a specific
  fleeting capture, a question, a topic he names), skips straight to working
  through that one thing. Either way, the point isn't the specific fact but
  the underlying principle it's an instance of - that's what actually gets
  learned and written down. Trigger on `/learning-foundations`, phrases like
  "what am I missing", "find gaps in my notes", "what should I learn next",
  or "help me flesh out <some note/topic>".
metadata:
  version: "1.0"
---

# Learning Foundations

The point of this skill is to find out what Oliver doesn't know and help him
actually learn it - not to generate content. A gap being *found* and a gap
being *learned* are different events; only the second one produces a file.
Never create a placeholder/stub note for a gap that hasn't actually been
worked through.

**Two ways in:** either run Step 1's scan and pick from what it finds, or
Oliver points straight at something - a fleeting capture that's just a raw
question (e.g. `Fleeting/Headless.md` containing only "what is headless") or a
topic he names in chat. In the second case, skip Step 1 entirely and go
straight to Step 2 for that one item - the interactive flow is identical
either way, only where the topic came from differs.

## Step 1 - Scan (read-only)

1. Read every file under `Notes/`, `MOCs/`, `Literature/`, `Fleeting/`, and the
   current `Foundations/Backlog.md`.
2. Extract every `[[wikilink]]` target from each note's body.
3. A **broken link** is a wikilink target with no matching file anywhere in the
   vault. Collect these, then rank by in-degree - how many distinct notes
   reference that same missing concept. Higher in-degree means more existing
   notes depend on it, i.e. more foundational.
4. Check each MOC: a section that lists no linked permanent/principle notes is
   a claimed-but-undeveloped topic - include it in the list too.
5. Look across clusters of notes that already link to each other for a shared
   idea that's implied but never named as its own `type: principle` note (e.g.
   several notes each independently explain a retry mechanism, but no note
   names the underlying idea, such as idempotency, that all of them rest on).
   This step is judgement, not link-counting - read the actual note content
   for this one.
6. Merge the results of steps 3-5 with whatever's already listed in
   `Foundations/Backlog.md`, de-duplicate, and present the combined, ranked
   list to Oliver in chat as a plain list he can pick from. **Do not write or
   modify any file in this step.**

## Step 2 - Attack one gap (interactive)

Wait for Oliver to pick one item from the Step 1 list. Then, for that item
only:

1. Ask what he already knows or assumes about it first. Don't launch into an
   explanation - the goal is finding out what's actually missing, not
   restating something he already has.
2. Discuss/explain the gap, explicitly connecting it to the notes that
   referenced it (from Step 1, if that's where it came from) and to any
   relevant `type: principle` notes already in the vault.
3. Explicitly ask: is there a more general principle this is an instance of,
   not just the specific fact/service/tool itself? Do this every time, not
   only when several existing notes already hint at the same pattern - the
   first time Oliver meets a concept is exactly when this should be asked,
   not after enough notes pile up to make it obvious in hindsight. If a real
   principle emerges, that's what gets quizzed on and written up as its own
   `type: principle` note - the specific thing becomes an example under it,
   not the other way round. If nothing more general is genuinely there,
   don't force one; write the specific note as `type: permanent` instead.
4. Keep going until Oliver can explain the concept - and the principle behind
   it, if one emerged - back in his own words.
5. Only then, help him write the note(s). He writes/dictates the actual content -
   don't write it for him wholesale. Your job is placing it correctly:
   - Frontmatter: `type: permanent` or `type: principle` (principle if it's an
     underlying idea rather than a specific fact), `tags`, `created`.
   - Filename/folder: `Notes/<Title>.md`.
   - Backlinks: add a link from this new note to whatever originally
     referenced it, and from those notes back to this one if not already
     linked.
   - Forward links: to any deeper principle this concept itself depends on.
   - Every other named concept mentioned in the note's body - not just the
     ones from this discussion - becomes a `[[wikilink]]` too, whether or not
     it has a note yet, same rule the Formatting skill uses in its Step 4.
     Otherwise a note written here never becomes scannable by Step 1 next
     time - a plain-text mention is invisible to it, only real wikilinks are.
   - MOC: insert a link into the right MOC section (same logic as the
     Formatting skill's MOC-linking step) - ask Oliver if no existing section
     fits.
6. Once the file(s) are written, remove the corresponding line from
   `Foundations/Backlog.md`, if it came from there.

## Step 3 - File the rest

Every gap surfaced in Step 1 that Oliver didn't pick this run gets written (or
rewritten, de-duplicated) into `Foundations/Backlog.md` as a plain checklist
line - source note referenced in parentheses, same style as existing entries.
Nothing found this run should be lost, and nothing should be written there
except a checklist line - no generated explanations, no stub content.
