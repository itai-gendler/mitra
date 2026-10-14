---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the cross beside a subtask in the bigger task's Subtasks row
  kind: actor
  actor: user
  entities:
  - {entity: subtask-link, effect: reads, facts: [Subtask]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes the link from the subtask
  kind: product
  actor: user
  entities:
  - {entity: subtask-link, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove a subtask from the bigger task

## Trigger

A task no longer belongs to the project.

## Outcome

The two tasks are no longer linked; the bigger task's count drops.
