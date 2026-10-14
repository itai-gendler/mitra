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
  target: src/features/entries/EntryType.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Change entry type

Turn an event into a task or a task into an event with Type in the editor's header, or an entry that does not repeat into availability. Calendar servers keep events and tasks apart, so Mitra saves the entry anew as the other type, deletes the old one, and keeps the editor open on the result. Whatever the new type cannot hold is dropped.
