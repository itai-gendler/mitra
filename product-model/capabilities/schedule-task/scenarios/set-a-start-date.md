---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Start date in the task's editor and picks a day
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Start, Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product schedules the task on that day and moves the view there, keeping the editor open
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End, All day, Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Schedule a task with Start date

## Trigger

On a phone, where there is nowhere to drag to, the user picks a day for a task.

## Outcome

The task starts at 9:00 for its estimate, or covers whole days when the estimate is a day or more; the view moves to that day with the task still open.
