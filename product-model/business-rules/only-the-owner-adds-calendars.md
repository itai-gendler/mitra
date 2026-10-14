---
appliesTo:
- type: entity
  id: calendar
  effect: creates
permits:
- related:
  - {verb: has, entity: integration}
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

# Only the owner of an integration adds calendars to it

Calendars join an integration when its owner connects or creates them, or when syncing finds them at the provider.
