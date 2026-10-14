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
  target: src/features/entries/client/EntryDragController.ts
- kind: code
  role: implementation
  target: src/features/relations/ShiftStrategy.ts
- kind: doc
  role: intent
  target: docs/dependencies.md
  title: Dependencies
---

# Move entry

Move an entry to another time by dragging it in a view, or change its length by dragging its edge. Dragging and resizing land on the Snap to step. When subtasks or dependent entries would be affected, or the entry repeats, Mitra asks what to move first; holding Ctrl (Cmd on a Mac) while dropping moves only this entry.
