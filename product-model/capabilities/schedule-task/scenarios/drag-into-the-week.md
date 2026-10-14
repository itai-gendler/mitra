---
kind: primary
routes:
  web: Web
steps:
- text: The User drags the task from the Unscheduled list onto Tuesday 9:00 in the week view
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Estimate]}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product schedules it from 9:00 for its estimate, or for the default duration without one
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default duration]}
  - {entity: task, effect: changes, facts: [Start, End, All day, Estimate]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Drag a task onto a time in the week

## Trigger

The user decides to prepare the presentation on Tuesday morning.

## Outcome

The task starts where it was dropped and lasts as long as its estimate; its due date stays.
