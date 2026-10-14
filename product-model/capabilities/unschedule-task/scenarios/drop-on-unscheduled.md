---
kind: primary
routes:
  web: Web
steps:
- text: The User drags a scheduled task from the week view onto the Unscheduled list
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product removes its start and end and keeps their length as the estimate
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End, Estimate, Reminders]}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# Drop a task on the Unscheduled list

## Trigger

A task will not happen this week after all.

## Outcome

The task is unscheduled, with its old length as its estimate.
