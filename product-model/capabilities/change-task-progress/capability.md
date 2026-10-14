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
  target: docs/subtasks.md
  title: Subtasks
---

# Change task progress

Set a progress by hand on a task with no subtasks and no checklist, by dragging Progress in the status menu in steps of 5%. The cross beside the value clears it. Calendar servers, Apple Calendar and Mitra calendars store progress; Google Calendar, Notion and Tempo do not.
