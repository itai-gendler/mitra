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
  target: src/features/entries/Checklist.ts
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Tick checklist item

Tick or untick a box of the checklist in an entry's description without editing the text. Mitra changes the box in the description, so other apps see it too; ticking boxes never changes a task's status.
