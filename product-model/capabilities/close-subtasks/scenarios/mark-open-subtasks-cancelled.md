---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens the subtask count in a closed task's status menu and chooses Mark as cancelled
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks each open subtask Cancelled
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Cancelled, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Mark the open subtasks cancelled

## Trigger

A project is dropped with the work under it.

## Outcome

The task's open subtasks are Cancelled.
