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

# Add subtask link

Make an entry a subtask of a bigger task by pressing the plus on Subtask of in the smaller entry's editor and searching the user's visible calendars for the bigger task. The link is always added from the subtask; the bigger task lists it under Subtasks with a count of how many are done. Google Calendar drops links, and subscriptions and Tempo have none.
