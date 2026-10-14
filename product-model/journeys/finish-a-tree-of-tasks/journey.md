---
actors:
- user
references:
- kind: code
  role: implementation
  target: src/features/relations/client/Hierarchy.ts#offerFollowUps
- kind: doc
  role: intent
  target: docs/subtasks.md
  title: Subtasks
---

# Finish a tree of tasks

## Goal

Close a task and the work under it in one go.

## Success criterion

The task and its open subtasks are closed.
