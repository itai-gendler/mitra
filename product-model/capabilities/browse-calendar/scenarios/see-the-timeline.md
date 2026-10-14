---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses L
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product lists the open tasks with a date, one per row, and only the due occurrences of repeating tasks
  kind: product
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title, Start, End, Repeat]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# See open tasks on the timeline

## Trigger

The user checks how their work lines up.

## Outcome

Each open task with a date has a row with a bar over its schedule, in date order; all-day events show along the top with their days shaded.
