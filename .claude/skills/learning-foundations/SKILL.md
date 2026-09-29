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

1. First check whether this item depends on a more basic/foundational
   concept that doesn't have its own note yet - e.g. a themed `Fleeting/`
   dump about specific details of a service, with no base note for the
   service itself (`SQS ApproximateAgeOfOldestMessage` presumes a reader
   already knows what SQS is; if `Notes/SQS.md` doesn't exist, that's the
   real starting point, not the specific detail). If so, attack that
   foundational concept first, through this same Step 2 process, before
   coming back to the item Oliver originally picked. Don't wait for this to
   be noticed by chance - check it every time, for every item, scan-found or
   directly pointed at.
2. Ask what he already knows or assumes about it first. Don't launch into an
   explanation - the goal is finding out what's actually missing, not
   restating something he already has.
3. Discuss/explain the gap as three distinct, clearly separated things, in
   this order - don't let them blur into one flowing explanation, or the
   what and why quietly get lost under mechanism detail:
   - **What**: a crisp, one- or two-sentence definition of the thing
     itself, stated plainly before anything else. State the concrete
     category it belongs to (a program, a protocol, a data structure, a
     service) before describing its function - a role word like
     "orchestrator" or "the thing that manages X" is still function
     dressed as identity, not the category itself. Both matter, but they
     answer different questions ("what kind of thing is this" vs "what
     does it do"), and only the category actually answers the first one.
   - **Why**: the fundamental constraint or problem that forces it to
     exist, derived from first principles - something that would still be
     true even if this specific technology didn't (e.g. not "SQS has a
     visibility timeout" as a fact to learn, but "a consumer can die
     silently and the queue has no way to know why - given only that,
     what's the only way to allow a retry without losing the message or
     blocking it forever?"). The mechanism should land as the necessary
     answer to that constraint, not an arbitrary detail to memorise. Don't
     force a derivation that isn't really there, though - some things
     genuinely are just a platform-imposed limit or convention with no
     deeper truth behind the specific value (CloudWatch's 86400s maximum
     alarm period isn't "necessary" from any constraint, it's just a chosen
     limit). If that's what it is, say so plainly instead of manufacturing
     a fake-sounding justification - a false derivation teaches something
     wrong dressed up as principled reasoning, worse than just stating it's
     arbitrary.
   - **How**: the actual mechanism, edge cases, and gotchas - only after
     what and why are both clearly on the table. This is where scenario
     detail and quiz-worthy nuance belongs; it shouldn't be where the
     definition and the reasoning are hiding.
   Then explicitly connect it to the notes that referenced it (from Step 1,
   if that's where it came from) and to any relevant `type: principle`
   notes already in the vault.
4. Explicitly ask: is there a more general principle this is an instance of,
   not just the specific fact/service/tool itself? Do this every time, not
   only when several existing notes already hint at the same pattern - the
   first time Oliver meets a concept is exactly when this should be asked,
   not after enough notes pile up to make it obvious in hindsight. If a real
   principle emerges, that's what gets quizzed on and written up as its own
   `type: principle` note - the specific thing becomes an example under it,
   not the other way round. If nothing more general is genuinely there,
   don't force one; write the specific note as `type: permanent` instead.
5. Quiz - don't just ask Oliver to "explain it back," which lets reciting the
   definition pass for understanding. Pose a concrete scenario or application
   question that requires actually using the concept (e.g. not "what is
   SQS again" but "Service B is down for an hour - what happens to messages
   sent to it via SQS vs a direct call, and why doesn't the sender see an
   error"), or - since step 3 derived the mechanism from a fundamental
   constraint rather than reciting it - a "why does it have to work this
   way" question that requires reproducing that derivation, not just
   applying the end result. After his answer, explicitly say whether it's correct,
   incorrect, or partially correct - don't quietly move on if it's close
   enough. If it's wrong or incomplete, don't reveal the correct answer -
   ask a narrowing follow-up (an analogy, a smaller version of the same
   question) and quiz again. Repeat until he produces a correct answer
   unprompted, in his own words. Do this for the specific concept, and
   separately for the principle behind it if one emerged in step 4.
6. Only then, help him write the note(s). He writes/dictates the actual content -
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
7. Once the file(s) are written, remove the corresponding line from
   `Foundations/Backlog.md`, if it came from there.

## Step 3 - File the rest

Every gap surfaced in Step 1 that Oliver didn't pick this run gets written (or
rewritten, de-duplicated) into `Foundations/Backlog.md` as a plain checklist
line - source note referenced in parentheses, same style as existing entries.
Nothing found this run should be lost, and nothing should be written there
except a checklist line - no generated explanations, no stub content.
