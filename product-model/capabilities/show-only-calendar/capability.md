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
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Show only calendar

Hide every other calendar with Only show this calendar in a calendar's menu, by Alt-clicking its eye, or from the command palette. Mitra remembers which calendars were showing.
