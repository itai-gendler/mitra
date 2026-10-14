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
  target: src/integrations/server/integrations.ts#integrationsRouter
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Re-import entries

Throw away Mitra's copy of a calendar's entries, or of a whole account's, and import them again from the provider with Re-import entries in the menu. Nothing at the provider changes. Mitra calendars do not offer it.
