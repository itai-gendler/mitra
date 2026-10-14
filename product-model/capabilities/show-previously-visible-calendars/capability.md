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

# Show previously visible calendars

Bring back the calendars that were showing before Only show this calendar, from the same menu item, the eye or the command palette.
