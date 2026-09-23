---
name: learning-note-formatting
description: >
  Use when Oliver hands over a rough/raw note or capture (often from
  Fleeting/) and wants it brought up to this vault's conventions - frontmatter,
  naming, folder placement, linking to existing concepts instead of creating
  duplicates, and filed into the right MOC. Trigger on
  `/learning-note-formatting` or phrases like "clean this note up", "format
  this", "tidy my fleeting notes".
metadata:
  version: "1.0"
---

# Learning Note Formatting

Mechanical tidying only - this skill doesn't decide what's true or teach
anything, it makes sure a note that's already been captured ends up correctly
placed and linked. See the `learning-foundations` skill for actually learning
new material.

## Step 1 - Check for existing concepts

Read the vault's `Notes/` and `MOCs/` before creating anything. If the concept
in the input already has a note under a different title, reuse and link to
that note rather than creating a near-duplicate - ask Oliver if it's ambiguous
which existing note (if any) it should be treated as the same concept as.

## Step 2 - Split if needed

Zettelkasten notes are one concept each. If the input covers more than one
distinct idea, split it into separate notes rather than one note with several
headings.

## Step 3 - Apply conventions

For each resulting note:

- Frontmatter: `type` (`permanent`, `principle`, `fleeting`, or `literature` -
  ask if it's not obviously ready to be a permanent note yet), `tags`,
  `created`.
- Filename: a short, clear title, matching the casing/style of existing notes
  in the vault.
- Folder: `Notes/` if ready as a permanent/principle note, `Literature/` if
  tied to a specific source, otherwise leave in `Fleeting/` rather than
  forcing it out before it's ready.

## Step 4 - Link

Convert plain-text mentions of concepts that already have a note into
`[[wikilinks]]`. Mentions of concepts that don't have a note yet should still
become `[[wikilinks]]`, not be stripped or left as plain text - that's exactly
the signal the Foundations skill looks for later.

## Step 5 - Normalise tags

Use lowercase-kebab-case tags, and check existing tags across the vault before
introducing a new one - reuse an existing tag over creating a near-duplicate
(e.g. don't add `iam-roles` if `iam` is already the tag in use).

## Step 6 - Link into the right MOC

Using the same `MOCs/` read from Step 1, find the MOC section this note
belongs under and add a link there. If no existing section fits (e.g. this is
the first note on a new topic), don't silently create a new MOC or section -
ask Oliver whether to create one or park the note under an existing section
for now. Placement mechanics (frontmatter, naming, linking to known concepts)
don't need a human; topic taxonomy does.
