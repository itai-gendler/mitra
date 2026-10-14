---
kind: alternative
routes:
  web: Web
steps:
- text: The User right-clicks the task's checkbox and picks Doing
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product sets the task to Doing
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Doing, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Pick a status from the status menu

## Trigger

The user starts working on a task.

## Outcome

The task is Doing.
