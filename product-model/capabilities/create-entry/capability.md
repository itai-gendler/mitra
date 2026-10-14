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
  target: src/features/entries/client/commands.ts#CreateEntry
- kind: code
  role: implementation
  target: src/features/entries/client/EntryDragController.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Create entry

Add an event or a task: by dragging across empty time in the week view, with Create or the C key, by drawing a task on the timeline's empty row, or with Add Task in the Planning tab. A new entry goes to the default calendar and starts with the default reminders for its kind; an entry with a time starts with the user's time zone.
