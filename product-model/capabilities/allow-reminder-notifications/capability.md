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
  target: src/features/reminders/client/NotificationsSetting.ts
---

# Allow reminder notifications

Let this browser alert the user with Allow on Reminder notifications; the browser asks for permission, and the browser becomes one of the user's devices. On an iPhone or iPad this works only in the installed app, and anywhere else only over HTTPS; where a browser cannot get notifications the row is missing.
