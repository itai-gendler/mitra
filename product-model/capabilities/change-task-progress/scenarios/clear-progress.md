---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the cross beside the progress
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product clears it
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Clear a task's progress

## Trigger

The progress set by hand no longer means anything.

## Outcome

The task carries no progress.
