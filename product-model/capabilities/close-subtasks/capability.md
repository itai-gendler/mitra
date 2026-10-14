---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/relations/client/DialogCloseSubtasks.ts
- kind: code
  role: implementation
  target: src/features/relations/client/Hierarchy.ts#offerToCloseSubtasks
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Close subtasks

Mark the open subtasks of a closed task done or cancelled at once, with Mark as done or Mark as cancelled. Mitra asks when a task is closed while subtasks are open, and the subtask count in the task's status menu leads to the same question later.
