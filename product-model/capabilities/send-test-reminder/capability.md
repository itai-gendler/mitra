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
---

# Send test reminder

Send a sample reminder to every device of the user with Test event or Test task.
