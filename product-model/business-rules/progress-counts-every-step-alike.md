---
appliesTo:
- type: entity
  id: task
  effect: reads
  facts: [Progress]
references:
- kind: code
  role: implementation
  target: src/features/relations/RelationGraph.ts
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Every subtask and checklist item counts as one step

A task's progress counts each subtask and each box of its checklist as one step of equal weight; a subtask partly done counts in part; cancelled subtasks and events linked as subtasks do not count. Only tasks count their checklists.
