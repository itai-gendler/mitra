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

# Rename time zone

Give a zone's column a label of the user's own, such as "Mom", with Rename on its name; renaming it to nothing brings back the automatic name. Naming the zone the user is in while travelling keeps it on their list.
