---
kind: primary
routes:
  web: Web
steps:
- text: The User drags a task to the top of the Unscheduled list
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Planning order]}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product saves the task's place in the order
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Planning order]}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# Drag a task up the Unscheduled list

## Trigger

One unscheduled task matters more than the rest.

## Outcome

The task keeps its new place, before tasks ordered only by due date, and keeps it when it moves to another calendar.

## Edge cases

- New tasks appear below the ones placed by hand, and finished tasks stay at the bottom.
