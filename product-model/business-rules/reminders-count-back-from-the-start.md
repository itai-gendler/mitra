---
appliesTo:
- type: capability
  id: send-reminder
- type: capability
  id: change-entry-reminders
- type: capability
  id: unschedule-task
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: code
  role: implementation
  target: src/features/reminders/server/ReminderScheduler.ts
---

# Reminders count back from the start, or from a due date

A reminder counts back from the entry's start or, for a task without a start, from its due date. Done and cancelled tasks stay silent, and calendars turned off stay silent; a hidden calendar still reminds. New timed entries start with the user's default reminders and all-day entries with none. Unscheduling a task keeps its reminders only while it has a due date.
