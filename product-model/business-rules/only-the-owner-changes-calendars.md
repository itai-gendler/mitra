---
appliesTo:
- type: entity
  id: calendar
  effect: changes
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
- kind: code
  role: implementation
  target: src/features/sources/server/sources.ts#sourcesRouter
---

# Only the owner of an integration changes its calendars

Naming, coloring, ordering, hiding, turning on and off and re-importing are the owner's own view of a calendar, so they work on read-only calendars too.
