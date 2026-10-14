---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/relations/server/relations.ts#assertRelationsValid
- kind: code
  role: implementation
  target: src/features/relations/client/RelationsField.ts
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Remove subtask link

Remove the link between a subtask and its bigger task with the cross beside it, from either side.
