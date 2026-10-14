---
appliesTo:
- type: capability
  id: schedule-task
- type: capability
  id: unschedule-task
- type: capability
  id: change-task-estimate
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# A task has an estimate only while it is unscheduled

When a task is scheduled its estimate becomes the length of its schedule; when it is unscheduled the length of its schedule becomes its estimate again, so nothing is lost either way.
