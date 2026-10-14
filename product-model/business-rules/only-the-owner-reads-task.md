---
appliesTo:
- type: entity
  id: task
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

# Only the user whose calendar holds them reads its tasks

A user sees the tasks of their own calendars only; on a server with several users nobody sees another user's. Reminders go out on Mitra's own schedule.
