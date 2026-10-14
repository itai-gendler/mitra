---
kind: alternative
routes:
  web: Web
steps:
- text: The User marks a task done that has open subtasks
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks it Done and asks whether to mark its open subtasks done or cancelled
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: Doing, to: Done, facts: [Progress]}
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Close a task while subtasks are open

## Trigger

The user marks a project done while some of its subtasks are still open.

## Outcome

The task is Done, and the Product carries the user into the question of what to do with the open subtasks.

## Edge cases

- Closing the question leaves the subtasks open; the subtask count in the status menu leads back to it.
