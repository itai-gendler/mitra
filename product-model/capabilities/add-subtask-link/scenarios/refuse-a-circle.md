---
kind: validation
routes:
  web: Web
steps:
- text: The User picks one of the task's own subtasks as its bigger task
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product refuses the link and shows why
  kind: product
  actor: user
  entities:
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Refuse a link that goes in a circle

## Trigger

The user tries to make a task a subtask of its own subtask.

## Outcome

Nothing is linked; the editor shows "This would create a circular hierarchy".

## Edge cases

- An entry cannot be linked to itself, and availability cannot be either end of a link.
