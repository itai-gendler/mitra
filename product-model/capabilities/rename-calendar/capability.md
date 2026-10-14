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

# Rename calendar

Give a calendar a name of the user's own by double-clicking it or with Rename in its menu. Syncing never overwrites it; Mitra takes the provider's name again only when the calendar is renamed there. Read-only calendars can be renamed too.
