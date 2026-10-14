---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Every month in the Repeat row of an unscheduled task with a due date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date, Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the rule anchored on the due date
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Repeat a task by its due date

## Trigger

The rent is due on the 1st of every month.

## Outcome

The unscheduled task repeats by its due date; the Unscheduled list shows only the next one, and it is never overdue.
