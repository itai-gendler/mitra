---
appliesTo:
- type: capability
  id: schedule-task
- type: capability
  id: unschedule-task
- type: capability
  id: move-entry
references:
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Scheduling, unscheduling and moving never change a task's due date

The due date is a constraint the schedule has to respect, never part of the schedule.
