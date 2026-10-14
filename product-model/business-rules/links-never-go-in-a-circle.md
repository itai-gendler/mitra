---
appliesTo:
- type: entity
  id: subtask-link
  effect: creates
- type: entity
  id: dependency
  effect: creates
references:
- kind: code
  role: implementation
  target: src/features/relations/server/relations.ts#assertRelationsValid
- kind: code
  role: implementation
  target: src/features/relations/RelationGraph.ts
---

# Subtask links and dependencies never go in a circle

Mitra refuses a link that would make a task a subtask of itself, directly or further down, or two entries each wait for the other. An entry cannot be linked to itself, and availability is never either end of a link.
