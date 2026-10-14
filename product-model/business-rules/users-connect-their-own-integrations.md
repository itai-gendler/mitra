---
appliesTo:
- type: entity
  id: integration
  effect: creates
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: code
  role: implementation
  target: src/integrations/server/integrations.ts#integrationsRouter
---

# Each user connects integrations only for themselves

An integration belongs to the user who connected it.
