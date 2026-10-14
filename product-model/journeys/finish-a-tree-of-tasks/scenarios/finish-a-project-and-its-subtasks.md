---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User marks the project task done
  kind: actor
  actor: user
  capability: change-task-status
  entities:
  - {entity: task, as: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks it Done and asks what to do with its open subtasks
  kind: product
  actor: user
  capability: change-task-status
  entities:
  - {entity: task, as: project, effect: changes, from: Doing, to: Done, facts: [Progress]}
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User chooses Mark as done
  kind: actor
  actor: user
  capability: close-subtasks
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks each open subtask Done
  kind: product
  actor: user
  capability: close-subtasks
  entities:
  - {entity: task, as: subtask, effect: changes, from: To Do, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Finish a project and its open subtasks

## Trigger

The user marks a project done while some of its subtasks are still open.

## Outcome

The project and every one of its open subtasks are Done.
