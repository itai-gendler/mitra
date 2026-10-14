---
appliesTo:
- type: capability
  id: reorder-tasks
- type: capability
  id: browse-planning
references:
- kind: code
  role: implementation
  target: src/features/entries/EntryRank.ts
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# The user's order comes before due dates

In the Unscheduled list the tasks the user placed come first in their order, then the rest by due date, soonest first, then alphabetically, with finished tasks at the bottom. The order is kept by Mitra alone and travels with a task to another calendar.
