---
kind: alternative
routes:
  web: Web
steps:
- text: The User adds At the time of the task to an unscheduled task with a due date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date, Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the reminder counted back from the due date
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remind before an unscheduled task's due date

## Trigger

An unscheduled task is due on Friday.

## Outcome

The reminder counts back from the due date.
