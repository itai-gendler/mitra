---
appliesTo:
- type: capability
  id: unschedule-task
- type: capability
  id: edit-entry
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
---

# Only tasks that do not repeat on a schedule lose their dates

An event always has a date, and a task that repeats on a schedule is made of its dates, so only other tasks can be unscheduled.
