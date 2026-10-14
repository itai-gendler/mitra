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
  target: src/features/entries/client/TaskStatus.ts
- kind: code
  role: implementation
  target: src/features/relations/client/Hierarchy.ts#offerFollowUps
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
---

# Change task status

Set a task to To Do, Doing, Done or Cancelled: the checkbox before its title marks it done and opens it back up, and right-clicking or Alt-clicking it opens the status menu with every status. It works in the editor and on the calendar, for the selected rows of the table, and from a reminder's Done button. A calendar without a cancelled status, like Notion, leaves Cancelled out.
