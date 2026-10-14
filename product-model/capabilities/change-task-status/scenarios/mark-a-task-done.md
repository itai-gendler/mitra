---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the task's checkbox
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product marks the task Done
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Mark a task done

## Trigger

The user finished a task.

## Outcome

The task is Done, struck through, silent, and at 100% where its calendar stores progress.

## Edge cases

- With Hide done tasks on, the task leaves the week, month and year views and the Planning tab once its editor closes.
