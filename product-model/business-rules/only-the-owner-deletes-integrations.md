---
appliesTo:
- type: entity
  id: integration
  effect: removes
permits:
- related:
  - {verb: owns, entity: user}
references:
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
---

# Only the owner deletes an integration

Only the user who connected an account disconnects it.
