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
  target: src/features/entries/client/EntryDetailsWhen.ts
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Change task due date

Give a task a due date with Due date in its editor, or take it away with the cross beside it. A task with a due date shows a small flag in the views and the Planning tab. Notion calendars hold no due date.
