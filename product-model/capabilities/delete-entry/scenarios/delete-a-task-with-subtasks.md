---
kind: alternative
routes:
  web: Web
steps:
- text: The User deletes a task that has subtasks
  kind: actor
  actor: user
  entities:
  - {entity: task, as: bigger-task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product asks Delete subtasks too?
  kind: product
  actor: user
  entities:
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User chooses to delete them too
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product deletes the subtasks and then the task
  kind: product
  actor: user
  entities:
  - {entity: task, as: subtask, effect: removes, from: To Do}
  - {entity: task, as: bigger-task, effect: removes, from: To Do}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Delete a task and its subtasks

## Trigger

A project is dropped altogether.

## Outcome

The task and every task below it are deleted, the deepest first.
