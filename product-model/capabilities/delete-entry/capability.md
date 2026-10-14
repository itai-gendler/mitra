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
  target: src/features/entries/client/DialogDeleteEntries.ts
- kind: doc
  role: intent
  target: docs/repeats.md
  title: Repeats
---

# Delete entry

Remove an entry with Delete in its editor's menu, the Delete or Backspace key while it is open, or the table view's Delete for the selected rows after asking. If it repeats or has subtasks, Mitra asks which entries are meant; Ctrl with Delete removes just this occurrence.
