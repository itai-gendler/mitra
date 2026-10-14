---
entities:
- entity: event
  shows: [Title, Start, End, Calendar, Location, Repeat, Reminders, Description]
- entity: task
  shows: [Title, Start, End, Calendar, Location, Repeat, Reminders, Description]
- entity: participant
  shows: [Email]
- entity: subtask-link
  shows: [Bigger task]
- entity: dependency
  shows: [Entry to finish first]
- entity: calendar
  shows: [Name]
entryPoints:
- web: /table
references:
- kind: code
  role: implementation
  target: src/features/calendar/client/Table.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/TableWindow.ts
- kind: doc
  role: intent
  target: docs/views/table.md
  title: Table view
---

# Table view

The user's entries as rows for a span of days counted from today, with undated tasks and overdue tasks always listed, to search, sort, filter and change many at once.
