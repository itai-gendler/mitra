---
availability:
- {place: 'web::signed-in'}
domain: calendars
references:
- kind: code
  role: implementation
  target: src/integrations/server/integrations.ts#integrationsRouter
- kind: code
  role: implementation
  target: src/integrations/client/DialogIntegration.ts
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Edit integration

Change an account under its menu's Edit: a new password or token, and which of its calendars are turned on. Refresh lists calendars created at the provider since the last sync. Turning a calendar off stops syncing and storing it, and takes back the busy availability written to it.
