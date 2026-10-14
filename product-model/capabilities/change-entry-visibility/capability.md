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
  target: src/features/entries/Visibility.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Change entry visibility

Choose what people the calendar is shared with learn of an entry: Default visibility, Public, Private or Confidential. Mitra saves the choice with the entry; the server and the apps reading it decide what to hide.
