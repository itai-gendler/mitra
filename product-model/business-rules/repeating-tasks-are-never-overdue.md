---
appliesTo:
- type: entity
  id: task
  effect: reads
  facts: [Overdue]
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Repeating tasks are never overdue

A task is overdue when it is open and its day, its due date or else the last day of its schedule, has passed, counted in whole days. A repeating task is never behind: the next occurrence settles the missed one.
