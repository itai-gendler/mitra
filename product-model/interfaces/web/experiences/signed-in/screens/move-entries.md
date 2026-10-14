---
entities:
- entity: calendar
  shows: [Name, Holds]
- entity: event
  shows: [Title, Repeat, Reminders]
- entity: task
  shows: [Title, Repeat, Due date, Estimate]
references:
- kind: code
  role: implementation
  target: src/features/migration/client/DialogSourceMigration.ts
- kind: code
  role: implementation
  target: src/features/migration/MigrationPlan.ts
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Move entries

Moving or copying a calendar's entries to another calendar: the destination, then what the move would cost before anything happens.
