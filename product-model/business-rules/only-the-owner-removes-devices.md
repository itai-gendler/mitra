---
appliesTo:
- type: entity
  id: device
  effect: removes
permits:
- related:
  - {verb: owns, entity: user}
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
---

# Only the owner removes a device

Removing a device stops its reminders.
