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

# Add time zone

Show the hours of another time zone in a column of the week view, with the plus at the top of the time column. The user's zones belong to their account and show on every device.
