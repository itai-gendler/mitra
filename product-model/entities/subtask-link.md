---
references:
- kind: code
  role: implementation
  target: src/features/relations/RelationType.ts#RelationType
- kind: code
  role: implementation
  target: src/features/relations/EntryRelation.ts
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Subtask link

Makes one entry a subtask of a bigger task. It is kept with the subtask, in that entry's own calendar, and the two may live in different calendars or accounts.

## Information kept

- **Subtask** — the smaller task, or an event linked as one
- **Bigger task** — the task it is part of
