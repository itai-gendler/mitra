---
appliesTo:
- type: entity
  id: device
  effect: reads
permits:
- related:
  - {verb: owns, entity: user}
- unattended: true
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
---

# Only the owner sees their devices

The Devices list shows the user's own devices only; reminders go out to them on Mitra's schedule.
