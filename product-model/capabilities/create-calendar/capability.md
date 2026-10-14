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
- kind: code
  role: implementation
  target: src/integrations/mitra/MitraCalendar.ts
- kind: doc
  role: intent
  target: docs/integrations/mitra.md
  title: Mitra calendars
---

# Create calendar

Add another Mitra calendar with New calendar in the menu on the Mitra heading. Calendars of connected accounts are created at their provider instead.
