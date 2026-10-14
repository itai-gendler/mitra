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
  target: docs/integrations/google.md
  title: Google Calendar
---

# Delete integration

Remove an account, and every calendar and entry Mitra keeps of it, with Delete in the account's menu. Nothing at the provider changes, except that busy availability written there is taken back first. Taking away Mitra's access happens at the provider.
