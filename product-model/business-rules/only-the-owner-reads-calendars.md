---
appliesTo:
- type: entity
  id: calendar
  effect: reads
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

# Only the user who connected an integration reads its calendars

Calendars, their names and colors are each user's own.
