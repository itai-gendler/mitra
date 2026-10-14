---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a weekly review task that repeats on a schedule
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product offers no way to remove its start
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Keep a date where it cannot go

## Trigger

The user tries to unschedule an event or a repeating task.

## Outcome

Nothing changes: an event always has a date, and a task that repeats on a schedule is made of its dates.
