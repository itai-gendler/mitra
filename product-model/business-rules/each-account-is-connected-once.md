---
appliesTo:
- type: capability
  id: add-integration
- type: entity
  id: integration
  effect: creates
references:
- kind: code
  role: implementation
  target: src/integrations/server/integrations.ts#integrationsRouter
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Each account is connected once

Connecting an account already in the sidebar is refused; it is changed under Edit instead. Connecting the same Google account again renews Mitra's access to it, and the Mitra integration is added once.
