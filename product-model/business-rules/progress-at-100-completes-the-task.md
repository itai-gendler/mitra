---
appliesTo:
- type: capability
  id: change-task-progress
- type: capability
  id: change-task-status
references:
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# A task at 100% is done

Setting a progress by hand to 100% makes the task Done; below 100% a done task goes back to Doing, and to To Do at 0%. Marking a task done sets its progress to 100% where the calendar stores progress.
