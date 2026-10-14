---
availability:
- {place: 'web::signed-in'}
domain: views
references:
- kind: code
  role: implementation
  target: src/features/identity/server/user.ts#userRouter
- kind: code
  role: implementation
  target: src/features/time/UserTimeZones.ts#UserTimeZones
- kind: code
  role: implementation
  target: src/features/time/client/TimeZones.ts
- kind: doc
  role: intent
  target: docs/time-zones.md
  title: Time zones
---

# Remove time zone

Take a zone's column away with Remove on its name, or by picking a ticked zone in the list. The current zone and home stay.
