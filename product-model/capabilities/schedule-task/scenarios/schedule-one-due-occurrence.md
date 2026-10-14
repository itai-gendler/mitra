---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags the next occurrence of a task that repeats by its due date into the week
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date, Repeat]}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product schedules that occurrence on its own
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End, Repeat]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Schedule this month's repeating task

## Trigger

The rent is due again; the user plans when to pay it.

## Outcome

Only this month's task is scheduled, as an entry of its own; next month's takes its place in the Unscheduled list.
