---
appliesTo:
- type: capability
  id: send-reminder
- type: capability
  id: snooze-reminder
- type: capability
  id: send-test-reminder
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/push.ts#pushRouter
---

# Every device of a user gets all their reminders

Reminders go to every browser or installed app where the user allowed notifications, each written in that device's language and time zone.
