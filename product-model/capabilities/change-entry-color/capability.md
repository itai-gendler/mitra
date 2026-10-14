---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Change entry color

Give one entry a color of its own with the dot at the start of the editor's header, or give it back its calendar's color with Reset to calendar color.
