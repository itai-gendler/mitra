---
kind: alternative
routes:
  web: Web
steps:
- text: The User marks the last open subtask done
  kind: actor
  actor: user
  entities:
  - {entity: task, as: subtask, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks it Done and asks whether to mark the bigger task done too
  kind: product
  actor: user
  entities:
  - {entity: task, as: subtask, effect: changes, from: To Do, to: Done, facts: [Progress]}
  - {entity: subtask-link, effect: reads, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User agrees
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product marks the bigger task Done, the deepest first when more tasks further up finish
  kind: product
  actor: user
  entities:
  - {entity: task, as: bigger-task, effect: changes, from: Doing, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Finish the last open subtask

## Trigger

The user ticks off the last open subtask of a bigger task whose checklist is fully ticked.

## Outcome

The subtask is Done and, when the user agrees, the bigger task and any it finishes further up are Done too.
