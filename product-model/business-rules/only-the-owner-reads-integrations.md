---
appliesTo:
- type: entity
  id: integration
  effect: reads
permits:
- related:
  - {verb: owns, entity: user}
- unattended: true
references:
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
---

# Only the user who connected an integration reads it

A user's connected accounts are their own.
