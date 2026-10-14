---
availability:
- {place: 'web::signed-in'}
domain: planning
references:
- kind: code
  role: implementation
  target: src/features/planning/client/Planning.ts
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Unschedule task

Take a task's schedule away and return it to the Planning tab: drag it out of a view onto the Unscheduled list, or press the cross beside its start date. The length of its schedule becomes its estimate, it keeps its due date, and its reminders stay only while a due date is left for them to count down to.
