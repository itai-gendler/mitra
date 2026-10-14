---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/reminders/server/ReminderScheduler.ts
- kind: code
  role: implementation
  target: src/features/reminders/ReminderNotification.ts
- kind: code
  role: implementation
  target: src/features/reminders/Reminders.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Send reminder

Remind the user of an event or task ahead of time, as a system notification on every device they allowed, even while Mitra is closed. A reminder counts back from the entry's start, or, for a task without a start, from its due date; a repeating entry reminds for each occurrence. Mitra itself sends it, with no other service to sign up for.
