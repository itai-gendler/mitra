---
appliesTo:
- type: capability
  id: tick-checklist-item
- type: entity
  id: task
  effect: changes
  facts: [Description]
references:
- kind: code
  role: implementation
  target: src/features/entries/Checklist.ts
---

# Ticking checklist boxes never changes a task's status

A box is changed in the description text only, so other apps see it; the status stays the user's to set.
