---
availability:
- {place: 'web::signed-in'}
domain: notifications
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
- kind: code
  role: implementation
  target: src/features/reminders/client/push.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
- kind: code
  role: implementation
  target: src/features/reminders/client/NotificationDevices.ts
---

# Rename device

Give one of the user's devices a name with the pencil beside it.
