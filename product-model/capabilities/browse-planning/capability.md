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
- kind: code
  role: implementation
  target: src/features/entries/server/entryWindow.ts
---

# Browse planning

Open the sidebar's Planning tab to see the tasks waiting for a place: Overdue, the most overdue first, and Unscheduled, in the user's order, then by due date, the soonest first, then alphabetically, with finished tasks at the bottom. The number on the tab counts both lists.
