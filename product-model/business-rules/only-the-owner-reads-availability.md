---
appliesTo:
- type: entity
  id: availability
  effect: reads
permits:
- related:
  - {verb: holds, entity: calendar}
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

# Only the user whose calendar holds them reads its availability

A user sees the availability of their own calendars only; on a server with several users nobody sees another user's. Reminders go out on Mitra's own schedule.
