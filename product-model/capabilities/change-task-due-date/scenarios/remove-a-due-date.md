---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the cross beside the due date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes it
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Due date]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove a due date

## Trigger

The deadline went away.

## Outcome

The task has no due date.
