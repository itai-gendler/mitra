---
availability:
- {place: 'web::signed-in'}
domain: notifications
references:
- kind: code
  role: implementation
  target: src/features/settings/client/DialogSettings.ts
- kind: code
  role: implementation
  target: src/app/settings.ts
- kind: doc
  role: intent
  target: docs/settings.md
  title: Settings
- kind: code
  role: implementation
  target: src/features/reminders/client/DefaultReminderSetting.ts
---

# Change notifications settings

Choose under Settings → Notifications the reminders new entries start with: Default event reminder, 30 minutes before unless changed, and Default task reminder, at the time of the task unless changed, or None. They apply only to entries with a time.
