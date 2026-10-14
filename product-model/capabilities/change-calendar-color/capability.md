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

# Change calendar color

Pick a calendar's color in its menu. Entries wear their calendar's color unless they have their own.
