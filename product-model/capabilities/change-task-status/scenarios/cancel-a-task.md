---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Cancelled in the status menu
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product sets the task to Cancelled
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: Doing, to: Cancelled, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Cancel a task

## Trigger

The user drops a task.

## Outcome

The task is Cancelled, struck through, and no longer holds back the bigger task's progress.
