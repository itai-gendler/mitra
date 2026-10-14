---
kind: alternative
routes:
  web: Web
steps:
- text: The User clicks the checkbox of a done task
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product sets the task back to To Do
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: Done, to: To Do, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Open a done task back up

## Trigger

A task turned out not to be finished.

## Outcome

The task is To Do again.
