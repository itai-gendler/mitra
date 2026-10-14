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

# Duplicate entry

Make a copy of an entry in the same calendar, with Duplicate in the editor's menu, which opens the copy, or by holding Alt while dragging, which drops the copy where it lands.
