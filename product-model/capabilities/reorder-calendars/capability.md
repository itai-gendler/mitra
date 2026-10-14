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

# Reorder calendars

Arrange the sidebar: drag a calendar up or down within its account, use Move up and Move down in its menu, or drag an account by its heading to move it with all its calendars. On a touch screen, press and hold before dragging.
