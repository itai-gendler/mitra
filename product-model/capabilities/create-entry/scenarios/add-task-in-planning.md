---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Add Task at the bottom of the Planning tab and types a title
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product saves an unscheduled task in the default calendar, or in the first calendar that can hold tasks if the default cannot
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: task, effect: creates, to: To Do, facts: [Title, Calendar]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# Note down a task in the Planning tab

## Trigger

The user wants to keep a task for later without deciding when to do it.

## Outcome

An unscheduled task with only a title waits in the Unscheduled list, below the tasks already placed.
