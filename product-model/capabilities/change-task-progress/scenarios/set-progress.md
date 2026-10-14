---
kind: primary
routes:
  web: Web
steps:
- text: The User drags Progress to 60%
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the progress and sets the task to Doing
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Doing, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Set a task's progress

## Trigger

A task is a little more than half done.

## Outcome

The task shows 60% in its checkbox outline and is Doing.

## Decision points

### Status follows progress

Where does the progress land?

- At 100% → the task becomes Done
- Below 100% on a done task → it goes back to Doing
- At 0% → it goes back to To Do
