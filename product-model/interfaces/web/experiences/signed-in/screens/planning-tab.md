---
entities:
- entity: task
  shows: [Title, Due date, Estimate, Planning order, Overdue, Progress, Calendar, Repeat]
  collects: [Title]
references:
- kind: code
  role: implementation
  target: src/features/planning/client/Planning.ts
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Planning tab

The sidebar's list of the tasks waiting for a place in the week: Overdue, the most overdue first, then Unscheduled in the user's order, with a count of both on the tab.
