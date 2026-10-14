---
appliesTo:
- type: entity
  id: calendar
  effect: removes
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

# Only the owner of an integration deletes its calendars

A user deletes their own Mitra calendars and disconnects their own accounts; syncing removes calendars deleted at the provider.
