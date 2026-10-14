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
- kind: code
  role: implementation
  target: src/features/entries/client/EventDetails.ts
- kind: code
  role: implementation
  target: src/features/entries/EntryPatch.ts#EntryPatch
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Edit entry

Change an entry's own facts in its editor: its title, description, location, start and end, and whether it is all day. Every change is saved as it is made, and goes back to the calendar the entry belongs to. Rows the calendar cannot store are hidden, so nothing typed is lost on the next sync.
