---
entities:
- entity: event
  shows: [Title, Start, Location]
- entity: task
  shows: [Title, Start, Due date, Location]
references:
- kind: code
  role: implementation
  target: src/features/reminders/ReminderNotification.ts
- kind: code
  role: implementation
  target: src/app/serviceWorker.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Reminder notification

The system notification a reminder arrives as, even while Mitra is closed: the entry's title, when it is and its location, in the device's language and time zone.
