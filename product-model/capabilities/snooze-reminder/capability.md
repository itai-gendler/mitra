---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
- kind: code
  role: implementation
  target: src/app/serviceWorker.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Snooze reminder

Bring a reminder back ten minutes later with Snooze 10 min on the notification. Safari and Firefox do not show the button.
