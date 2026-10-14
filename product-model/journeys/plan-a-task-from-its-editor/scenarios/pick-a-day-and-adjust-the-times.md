---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User presses Start date in the task's editor and picks a day
  kind: actor
  actor: user
  capability: schedule-task
  entities:
  - {entity: task, effect: reads, facts: [Start, Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product schedules it from 9:00 for its estimate and moves the view to that day, keeping the editor open
  kind: product
  actor: user
  capability: schedule-task
  entities:
  - {entity: task, effect: changes, facts: [Start, End, All day, Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User changes the start to 14:00
  kind: actor
  actor: user
  capability: edit-entry
  entities:
  - {entity: task, effect: reads, facts: [Start]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the new start and end
  kind: product
  actor: user
  capability: edit-entry
  entities:
  - {entity: task, effect: changes, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Pick a day and adjust the times

## Trigger

On a phone, the user decides when to work on a task.

## Outcome

The task is scheduled on the picked day at the adjusted times.
