---
appliesTo:
- type: entity
  id: integration
  effect: changes
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

# Only the owner changes an integration

Only the user who connected an account changes its password, its calendars or its place in the sidebar.
