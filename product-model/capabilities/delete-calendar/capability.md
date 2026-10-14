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
  target: src/features/sources/client/DialogSourceDeletion.ts#DialogSourceDeletion
- kind: doc
  role: intent
  target: docs/integrations/mitra.md
  title: Mitra calendars
---

# Delete calendar

Delete a Mitra calendar, with all of its entries for good, with Delete calendar in its menu. When it still has entries Mitra asks first and offers Move entries first…. Calendars of connected accounts are deleted at their provider, and Mitra notices on its next sync.
