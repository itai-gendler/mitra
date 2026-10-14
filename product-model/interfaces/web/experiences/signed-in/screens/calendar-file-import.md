---
entities:
- entity: calendar
  shows: [Name, Holds]
- entity: event
  shows: [Title]
- entity: task
  shows: [Title]
references:
- kind: code
  role: implementation
  target: src/features/migration/client/DialogIcsImport.ts
- kind: doc
  role: intent
  target: docs/calendar-files.md
  title: Calendar files
---

# Add calendar file

Adding the entries of a calendar file: the calendar to add them to, then what that calendar cannot store, before anything is added.
