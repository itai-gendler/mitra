---
entities:
- entity: integration
  shows: [Provider, Connection details]
  collects: [Connection details, Secret]
- entity: calendar
  shows: [Name, Holds]
entryPoints:
- web: /?subscribe=
references:
- kind: code
  role: implementation
  target: src/integrations/client/DialogIntegration.ts
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Integration details

Where an integration is connected or edited: the provider's form, then the calendars found in the account, each saying what it holds and whether it is turned on.
