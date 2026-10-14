---
appliesTo:
- type: capability
  id: create-calendar
- type: capability
  id: delete-calendar
references:
- kind: code
  role: implementation
  target: src/integrations/mitra/MitraCalendar.ts
- kind: code
  role: implementation
  target: src/integrations/server/integrations.ts#integrationsRouter
---

# Only Mitra calendars are created and deleted in Mitra

A calendar of a connected account is created and deleted at its provider, and Mitra notices on its next sync. Mitra calendars are created with New calendar and deleted with Delete calendar.
