---
availability:
- {place: 'web::signed-in'}
domain: calendars
references:
- kind: code
  role: implementation
  target: src/features/sources/server/sources.ts#sourcesRouter
- kind: code
  role: implementation
  target: src/app/Sidebar.ts
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Hide calendar

Hide a calendar's entries and availability with the eye at the end of its row. Hiding is only about what the user sees: the calendar keeps syncing and its reminders still go off.
