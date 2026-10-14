---
kind: alternative
routes:
  web: Web
steps:
- text: The User drops the task in the all-day lane, or on a day of the month or year view
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Estimate]}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product schedules it all-day over its estimate's days
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End, All day, Estimate]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Drop a task on a day

## Trigger

A two-day task belongs to next week.

## Outcome

The task is all-day, covering as many days as its estimate and at least one.
