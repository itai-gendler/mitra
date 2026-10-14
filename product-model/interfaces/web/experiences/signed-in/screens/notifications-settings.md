---
entities:
- entity: user
  shows: [Default event reminder, Default task reminder]
  collects: [Default event reminder, Default task reminder]
- entity: device
  shows: [Name, This device]
  collects: [Name]
- entity: device-settings
  shows: [Reminder notifications]
references:
- kind: code
  role: implementation
  target: src/features/reminders/client/NotificationDevices.ts
- kind: code
  role: implementation
  target: src/features/reminders/client/NotificationsSetting.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Notifications settings

Whether this browser may alert the user, the reminders new entries start with, and the user's devices once this browser allows notifications.
