---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Mark as done
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks each open subtask of the task Done
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Mark the open subtasks done

## Trigger

A project is finished, and so is the work under it.

## Outcome

The task's open subtasks are Done.
