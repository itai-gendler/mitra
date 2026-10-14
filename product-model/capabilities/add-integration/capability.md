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
  target: src/integrations/server/Importer.ts
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Add integration

Connect an account, or add Mitra calendars, with Add Integration at the foot of the sidebar. Mitra finds the account's calendars and lists them, all ticked, each saying what it holds; the user unticks the ones they do not want and saves, and Mitra imports the rest in the background. Each account can be connected once. Google Calendar is offered only while the server is set up for it, and the Mitra integration, once added, holds as many calendars as the user likes.
