---
appliesTo:
- type: entity
  id: device
  effect: changes
permits:
- related:
  - {verb: owns, entity: user}
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
---

# Only the owner renames a device

A device's name is its owner's.
