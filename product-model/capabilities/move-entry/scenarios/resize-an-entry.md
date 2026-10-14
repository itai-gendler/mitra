---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags the end edge of a scheduled task
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product saves the new end
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Resize an entry

## Trigger

A task will take longer than planned.

## Outcome

The task ends later and keeps its start.
