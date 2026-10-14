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

# Make home time zone

Make another zone the user's home with Make home on its name; the old home stays as a column until it is removed. The first device the user opens Mitra on sets home.
