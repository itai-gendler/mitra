---
appliesTo:
- type: entity
  id: device
  effect: creates
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
---

# Each user registers devices only for themselves

Allowing notifications makes the browser a device of the user who allowed them; a browser taken over by another user loses its name.
