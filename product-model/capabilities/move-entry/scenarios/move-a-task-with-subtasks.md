---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags a task that has subtasks
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Start]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product asks Move subtasks too?
  kind: product
  actor: user
  entities:
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The User chooses to move the subtasks too
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product moves the task and each of its dated subtasks by the same amount of time
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Move a task with its subtasks

## Trigger

A project task moves to next week.

## Outcome

The task moves, and its dated subtasks move by the same amount when the user asks for it.
